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
ms.openlocfilehash: 44ae5d9cbfbabc5615a751dba5f6c13290fc7b35
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405632"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="dcf59-103">Обзор обработки формы (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="dcf59-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="dcf59-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="dcf59-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="dcf59-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="dcf59-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="dcf59-106">Project Кортекс использует обработку формы [AI-построителя](https://docs.microsoft.com/ai-builder/overview) Microsoft PowerApps для создания моделей в библиотеках документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dcf59-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="dcf59-107">С помощью обработки форм в построителе AI можно создавать модели AI, использующие технологию машинного обучения для идентификации и извлечения пар "ключ-значение" и табличных данных из структурированных или частично структурированных документов, таких как формы и счета.</span><span class="sxs-lookup"><span data-stu-id="dcf59-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="dcf59-108">Компании часто получают накладные в больших объемах и из различных источников, таких как почта, Факс, электронная почта или пользователь.</span><span class="sxs-lookup"><span data-stu-id="dcf59-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="dcf59-109">Обработка этих документов и ручное их ввод в базу данных может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="dcf59-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="dcf59-110">С помощью AI для извлечения из документов, пар "текст", пар "ключ-значение" и таблиц из документов обработка форм будет автоматизировать этот процесс.</span><span class="sxs-lookup"><span data-stu-id="dcf59-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="dcf59-111">Например, можно создать модель обработки форм, которая будет определять все документы заказа на покупку, отправленные в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="dcf59-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="dcf59-112">В каждом заказе на покупку можно извлекать и отображать конкретные данные, которые важны для вас, например *номер заказа на покупку*, *дату*или *общую стоимость*.</span><span class="sxs-lookup"><span data-stu-id="dcf59-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="dcf59-113">Для обучения модели и определения сведений, извлекаемых из формы, используются примеры файлов.</span><span class="sxs-lookup"><span data-stu-id="dcf59-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="dcf59-114">Макет документа рассказано в вашей модели.</span><span class="sxs-lookup"><span data-stu-id="dcf59-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="dcf59-115">Чтобы начать работу, вам потребуется пять документов формы.</span><span class="sxs-lookup"><span data-stu-id="dcf59-115">You only need five form documents to get started.</span></span> <span data-ttu-id="dcf59-116">В построителе AI анализируются файлы с примерами для пар "ключ-значение", а также могут быть определены вручную необнаруженные.</span><span class="sxs-lookup"><span data-stu-id="dcf59-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="dcf59-117">С помощью AI Builder можно проверить точность модели в примерах файлов.</span><span class="sxs-lookup"><span data-stu-id="dcf59-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="dcf59-118">После того как вы Научите и опубликуете модель, для ее использования вы создадите [автоматизированное управление питанием](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="dcf59-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="dcf59-119">Поток выполняется, когда файл загружается в библиотеку документов SharePoint, и извлекаются данные, идентифицированные в модели.</span><span class="sxs-lookup"><span data-stu-id="dcf59-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="dcf59-120">Извлеченные данные будут отображаться в столбцах представления библиотеки документов модели.</span><span class="sxs-lookup"><span data-stu-id="dcf59-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="dcf59-121">Администратору Office 365 необходимо [включить обработку формы](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) для библиотеки документов SharePoint, чтобы пользователи могли создавать в ней [модель обработки форм](create-a-form-processing-model.md) .</span><span class="sxs-lookup"><span data-stu-id="dcf59-121">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="dcf59-122">См. также</span><span class="sxs-lookup"><span data-stu-id="dcf59-122">See Also</span></span>
  
[<span data-ttu-id="dcf59-123">Документация по автоматизации управления питанием</span><span class="sxs-lookup"><span data-stu-id="dcf59-123">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="dcf59-124">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="dcf59-124">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="dcf59-125">Общие сведения о документе</span><span class="sxs-lookup"><span data-stu-id="dcf59-125">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="dcf59-126">Обучение: повышение производительности бизнеса с помощью построителя AI</span><span class="sxs-lookup"><span data-stu-id="dcf59-126">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




