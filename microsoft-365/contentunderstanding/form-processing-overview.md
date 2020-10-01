---
title: Общие сведения об обработке форм
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Узнайте об обработке форм в Microsoft SharePoint Syntex
ms.openlocfilehash: 4917f2db50827490dccb7fc85889b0df99909c39
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321760"
---
# <a name="form-processing-overview"></a><span data-ttu-id="3bd2c-103">Общие сведения об обработке форм</span><span class="sxs-lookup"><span data-stu-id="3bd2c-103">Form processing overview</span></span>

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="3bd2c-105">Средство Microsoft SharePoint Syntex использует функцию обработки форм приложения Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) для создания моделей в библиотеках документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="3bd2c-106">Вы можете использовать функцию обработки форм AI Builder для создания моделей ИИ, использующих технологию машинного обучения для поиска и извлечения пар вида "ключ и значение" и табличных данных из структурированных или частично структурированных документов, таких как формы и счета.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="3bd2c-107">Организации часто получают большое количество счетов по различным каналам, таким как почта, факс, электронная почта и т. д. Обработка этих документов и внесение их в базу данных вручную может занимать очень много времени.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="3bd2c-108">Применяя ИИ для извлечения из ваших документов текста, пар "ключ и значение" и табличных данных, функция обработки форм автоматизирует этот процесс.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

<span data-ttu-id="3bd2c-109">Например, можно создать модель обработки форм, которая найдет все заказы на покупку, загруженные в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-109">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="3bd2c-110">Затем вы можете извлечь из каждого заказа и отобразить не или иные сведения, представляющие для вас важность, например *Номер заказа*, *Дата* или *Общая стоимость*.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-110">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Представление библиотеки документов](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="3bd2c-112">Кроме того, вы можете использовать образцы файлов, чтобы обучить модель, указав, какие данные нужно извлекать из форм.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-112">You can also use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="3bd2c-113">Во время обучения модель усваивает структуру ваших документов и учится извлекать данные из похожих мест в формах, так как они имеют аналогичную структуру.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-113">The layout of your document is learned by training your model, and it learns to extract your data from similar locations in your forms since they have a similar structured layout.</span></span> 

<span data-ttu-id="3bd2c-114">Чтобы приступить к работе, вам нужно не менее пяти форм.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-114">You need a minimum of five form documents to get started.</span></span> <span data-ttu-id="3bd2c-115">Процесс построения ИИ включает анализ ваших образцов файлов на предмет пар "ключ/значение" и указание вручную тех пар, которые могли быть пропущены.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-115">AI building analyzes your example files for key-value pairs, and then manually identifies the ones that may not have been detected.</span></span>  <span data-ttu-id="3bd2c-116">AI Builder позволяет протестировать точность работы модели на образцах файлов.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-116">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="3bd2c-117">После обучения и публикации вашей модели создайте с ее помощью рабочий процесс [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started), который будет выполняться после загрузки файла в библиотеку документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-117">After you train and publish your model, use it to create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that runs after a file is uploaded to the SharePoint document library.</span></span> <span data-ttu-id="3bd2c-118">В результате процесса извлекаются данные, определенные в модели.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-118">It then extracts data that has been identified in the model.</span></span> <span data-ttu-id="3bd2c-119">Извлеченные данные будут отображаться в столбцах в представлении библиотеки документов вашей модели.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="3bd2c-120">Вы можете использовать образцы файлов, чтобы обучить модель, указав, какие данные нужно извлекать из форм.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-120">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="3bd2c-121">Во время обучения модель усваивает структуру ваших документов.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-121">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="3bd2c-122">Чтобы приступить к работе, вам нужно всего пять форм.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-122">You only need five form documents to get started.</span></span> <span data-ttu-id="3bd2c-123">Приложение AI Builder проанализирует ваши образцы файлов на предмет пар "ключ/значение", а те пары, которые могли быть пропущены, вы можете указать вручную.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-123">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="3bd2c-124">AI Builder позволяет протестировать точность работы модели на образцах файлов.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-124">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="3bd2c-125">После обучения и публикации вашей модели она создаст рабочий процесс [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="3bd2c-125">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="3bd2c-126">Этот процесс будет выполняться при загрузке файла в библиотеку документов SharePoint, извлекая данные, указанные в модели.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-126">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="3bd2c-127">Извлеченные данные будут отображаться в столбцах в представлении библиотеки документов вашей модели.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-127">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="3bd2c-128">Администратору Office 365 необходимо [включить функцию обработки форм](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) для библиотеки документов SharePoint, чтобы пользователи могли [создавать модели обработки форм](create-a-form-processing-model.md) в этой библиотеке.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-128">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="3bd2c-129">См. также</span><span class="sxs-lookup"><span data-stu-id="3bd2c-129">See Also</span></span>
  
[<span data-ttu-id="3bd2c-130">Документация Power Automate</span><span class="sxs-lookup"><span data-stu-id="3bd2c-130">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="3bd2c-131">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="3bd2c-131">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="3bd2c-132">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="3bd2c-132">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="3bd2c-133">Учебный курс. Повышение продуктивности бизнеса с помощью AI Builder</span><span class="sxs-lookup"><span data-stu-id="3bd2c-133">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
