---
title: REST API модели осмысления документации SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Обзор REST API модели осмысления документа SharePoint Syntex.
ms.openlocfilehash: e661df76828db0d05f7c3492880259117b9f8bf1
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908093"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="1a853-103">REST API модели осмысления документации SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="1a853-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="1a853-104">С помощью интерфейса REST в SharePoint можно создать модель осмысления документации, применить или удалить модель в одной или нескольких библиотеках, а также получить или обновить сведения о модели.</span><span class="sxs-lookup"><span data-stu-id="1a853-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="1a853-105">Служба REST в SharePoint Online (а также локальной среде SharePoint 2016 или более поздней версии) поддерживает объединение нескольких запросов в один вызов службы с помощью параметра запроса OData $batch.</span><span class="sxs-lookup"><span data-stu-id="1a853-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="1a853-106">Подробные сведения и ссылки на примеры кода см. в статье [Отправка пакетных запросов с помощью интерфейсов REST API](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span><span class="sxs-lookup"><span data-stu-id="1a853-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1a853-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1a853-107">Prerequisites</span></span>

<span data-ttu-id="1a853-108">Прежде чем приступить к работе, убедитесь, что вы знакомы с понятиями, описанными в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="1a853-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="1a853-109">Знакомство со службой REST в SharePoint</span><span class="sxs-lookup"><span data-stu-id="1a853-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [<span data-ttu-id="1a853-110">Выполнение базовых операций с использованием конечных точек REST SharePoint</span><span class="sxs-lookup"><span data-stu-id="1a853-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a><span data-ttu-id="1a853-111">Команды REST</span><span class="sxs-lookup"><span data-stu-id="1a853-111">REST commands</span></span>

<span data-ttu-id="1a853-112">Для работы с моделями осмысления документации Syntex доступны следующие команды REST.</span><span class="sxs-lookup"><span data-stu-id="1a853-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="1a853-113">[Создать модель](rest-createmodel-method.md) — создает модель и связанный тип контента.</span><span class="sxs-lookup"><span data-stu-id="1a853-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="1a853-114">[GetByUniqueId](rest-getbyuniqueid-method.md) — получает или обновляет сведения о модели осмысления документации SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="1a853-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="1a853-115">[GetByTitle](rest-getbytitle-method.md) — получает или обновляет сведения о модели осмысления документации SharePoint Syntex с помощью названия модели.</span><span class="sxs-lookup"><span data-stu-id="1a853-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="1a853-116">[Применить модель](rest-applymodel-method.md) — применяет (или синхронизирует) обученную модель осмысления документации к одной или нескольким библиотекам.</span><span class="sxs-lookup"><span data-stu-id="1a853-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="1a853-117">[Получить сведения о модели и библиотеке](rest-getmodelandlibraryinfo.md) — получает сведения о модели и библиотеке, к которой она была применена.</span><span class="sxs-lookup"><span data-stu-id="1a853-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="1a853-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) — обновляет доступные параметры моделей (связанную метку хранения и описание модели) для модели осмысления документации SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="1a853-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="1a853-119">[BatchDelete](rest-batchdelete-method.md) — удаляет примененную модель осмысления документации из одной или нескольких библиотек.</span><span class="sxs-lookup"><span data-stu-id="1a853-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="1a853-120">[Создать запрос классификации](rest-createclassificationrequest.md) — создает запрос на классификацию указанного файла или файлов с помощью примененной модели.</span><span class="sxs-lookup"><span data-stu-id="1a853-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="1a853-121">Сценарии</span><span class="sxs-lookup"><span data-stu-id="1a853-121">Scenarios</span></span>

<span data-ttu-id="1a853-122">Обратите внимание, что имя метода не всегда отражает суть следующих примеров сценариев.</span><span class="sxs-lookup"><span data-stu-id="1a853-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="1a853-123">Дополнительные сведения см. в отдельных статьях.</span><span class="sxs-lookup"><span data-stu-id="1a853-123">For more information, see each article.</span></span>

<span data-ttu-id="1a853-124">Метод создания модели создает только объект модели и связанный тип контента.</span><span class="sxs-lookup"><span data-stu-id="1a853-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="1a853-125">Сначала необходимо обучить модель в центре контента, прежде чем ее можно будет применить к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="1a853-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="1a853-126">Метод применения модели используется для настройки модели в целевой библиотеке, чтобы классифицировать документы и при желании извлекать дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="1a853-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="1a853-127">Этот API также поддерживает пакетное применение модели к нескольким библиотекам.</span><span class="sxs-lookup"><span data-stu-id="1a853-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="1a853-128">Метод удаления модели просто удаляет модель из одной или нескольких библиотек, к которым она была применена ранее.</span><span class="sxs-lookup"><span data-stu-id="1a853-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="1a853-129">Если вы хотите удалить модель, ее необходимо сначала удалить из всех библиотек, к которым она была применена.</span><span class="sxs-lookup"><span data-stu-id="1a853-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="1a853-130">См. также</span><span class="sxs-lookup"><span data-stu-id="1a853-130">See also</span></span>

[<span data-ttu-id="1a853-131">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="1a853-131">Document understanding overview</span></span>](../document-understanding-overview.md)

