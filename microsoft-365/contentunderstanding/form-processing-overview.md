---
title: Обзор обработки формы (Предварительная версия)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Сведения об обработке форм в Project кортекс.
ms.openlocfilehash: dbea06cdf2dbb232a7ea48c78d7ea968dd18b9c0
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612730"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="b6788-103">Обзор обработки формы (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="b6788-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="b6788-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="b6788-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="b6788-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="b6788-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="b6788-106">Project Кортекс использует обработку формы [AI-построителя](https://docs.microsoft.com/ai-builder/overview) Microsoft PowerApps для создания моделей в библиотеках документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b6788-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="b6788-107">С помощью обработки форм в построителе AI можно создавать модели AI, использующие технологию машинного обучения для идентификации и извлечения пар "ключ-значение" и табличных данных из структурированных или частично структурированных документов, таких как формы и счета.</span><span class="sxs-lookup"><span data-stu-id="b6788-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like form and invoices.</span></span>

<span data-ttu-id="b6788-108">Компании часто получают накладные в больших объемах и из различных источников, таких как почта, Факс, электронная почта или пользователь.</span><span class="sxs-lookup"><span data-stu-id="b6788-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="b6788-109">Обработка этих документов и ручное их ввод в базу данных может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="b6788-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="b6788-110">С помощью AI для извлечения из документов, пар "текст", пар "ключ-значение" и таблиц из документов обработка форм будет автоматизировать этот процесс.</span><span class="sxs-lookup"><span data-stu-id="b6788-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="b6788-111">Например, можно создать модель обработки форм, которая будет определять все документы заказа на покупку, отправленные в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="b6788-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="b6788-112">В каждом заказе на покупку можно извлекать и отображать конкретные данные, которые важны для вас, например *номер заказа на покупку*, *дату*или *общую стоимость*.</span><span class="sxs-lookup"><span data-stu-id="b6788-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="b6788-113">Для обучения модели и определения сведений, извлекаемых из формы, используются примеры файлов.</span><span class="sxs-lookup"><span data-stu-id="b6788-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="b6788-114">Макет документа рассказано в вашей модели.</span><span class="sxs-lookup"><span data-stu-id="b6788-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="b6788-115">Чтобы начать работу, вам потребуется пять документов формы.</span><span class="sxs-lookup"><span data-stu-id="b6788-115">You only need five form documents to get started.</span></span> <span data-ttu-id="b6788-116">При построении AI файлы примера анализируются для пар "ключ-значение", а также могут быть определены вручную необнаруженные.</span><span class="sxs-lookup"><span data-stu-id="b6788-116">AI building will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="b6788-117">С помощью AI Builder можно проверить точность модели в примерах файлов.</span><span class="sxs-lookup"><span data-stu-id="b6788-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="b6788-118">После того как вы Научите и опубликуете модель, для ее использования вы создадите [поток автоматизации Power](https://docs.microsoft.com/power-automate/getting-started) , который будет выполняться при загрузке файла в библиотеку документов SharePoint и будет извлекать данные, идентифицированные в модели.</span><span class="sxs-lookup"><span data-stu-id="b6788-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that will run when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="b6788-119">Извлеченные данные будут отображаться в столбцах представления библиотеки документов модели.</span><span class="sxs-lookup"><span data-stu-id="b6788-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="b6788-120">Администратору Office 365 необходимо [включить обработку формы](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) для библиотеки документов SharePoint, чтобы пользователи могли создавать в ней [модель обработки форм](create-a-form-processing-model.md) .</span><span class="sxs-lookup"><span data-stu-id="b6788-120">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="b6788-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b6788-121">See Also</span></span>
  
[<span data-ttu-id="b6788-122">Документация по автоматизации управления питанием</span><span class="sxs-lookup"><span data-stu-id="b6788-122">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="b6788-123">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="b6788-123">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="b6788-124">Общие сведения о документе</span><span class="sxs-lookup"><span data-stu-id="b6788-124">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="b6788-125">Обучение: повышение производительности бизнеса с помощью построителя AI</span><span class="sxs-lookup"><span data-stu-id="b6788-125">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




