---
title: Расширенная индексация данных для расследования
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как использовать расширенную индексацию, чтобы убедиться, что поиск захватывает все данные, которые вы хотите исследовать.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b0bb1a757ac70466fb43f2385485ce6da1dc741
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285965"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="ebf48-103">Расширенная индексация данных для расследования</span><span class="sxs-lookup"><span data-stu-id="ebf48-103">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="ebf48-104">Содержимое в действующей системе может частично индексироваться по ряду причин, в том числе наличия изображений, неподдерживаемых типов файлов или при обнаружении ограничения на размер файлов индексирования.</span><span class="sxs-lookup"><span data-stu-id="ebf48-104">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="ebf48-105">При использовании сброса данных с высоким уровнем риска необходимо убедиться, что поиск сохранил все данные, которые нужно исследовать.</span><span class="sxs-lookup"><span data-stu-id="ebf48-105">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="ebf48-106">Когда интересующий пользователь добавляется к расследованию данных, все содержимое, которое было признано частично индексированным, переобрабатывается, чтобы сделать его полным поиском.</span><span class="sxs-lookup"><span data-stu-id="ebf48-106">When a person of interest is added to a Data investigation, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span> <span data-ttu-id="ebf48-107">Этот процесс называется *расширенной индексацией*.</span><span class="sxs-lookup"><span data-stu-id="ebf48-107">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="ebf48-108">Дополнительные сведения о поддержке обработки и частично индексированных элементах приведены в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ebf48-108">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="ebf48-109">Поддерживаемые типы файлов при расследовании данных</span><span class="sxs-lookup"><span data-stu-id="ebf48-109">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="ebf48-110">Частично индексированные элементы в средстве "Поиск контента" в Office 365</span><span class="sxs-lookup"><span data-stu-id="ebf48-110">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="ebf48-111">Форматы файлов, индексируемые службой поиска Exchange</span><span class="sxs-lookup"><span data-stu-id="ebf48-111">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="ebf48-112">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="ebf48-112">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="ebf48-113">Просмотр результатов расширенного индексирования</span><span class="sxs-lookup"><span data-stu-id="ebf48-113">Viewing Advanced indexing results</span></span>

<span data-ttu-id="ebf48-114">После выполнения расширенного процесса индексирования можно получить сведения о эффективности повторной обработки.</span><span class="sxs-lookup"><span data-stu-id="ebf48-114">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="ebf48-115">В представлении индексирование интересов на диаграмме представлены все элементы, добавленные в *гибридный индекс*.</span><span class="sxs-lookup"><span data-stu-id="ebf48-115">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="ebf48-116">Гибридный индекс — это место хранения повторно обработанного контента при расследовании данных (Предварительная версия).</span><span class="sxs-lookup"><span data-stu-id="ebf48-116">The hybrid index is where Data Investigations (preview) stores the reprocessed content.</span></span>

<span data-ttu-id="ebf48-117">На диаграмме также представлено количество элементов, для которых требуется исправление, и еще один график ошибок по типам файлов.</span><span class="sxs-lookup"><span data-stu-id="ebf48-117">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="ebf48-118">Дополнительные сведения см. в разделе [Устранение ошибок при обработке данных](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="ebf48-118">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="ebf48-119">Обновление расширенных индексов для интересующих людей</span><span class="sxs-lookup"><span data-stu-id="ebf48-119">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="ebf48-120">Когда интересующий пользователь добавляется в анализ данных, все частично индексированные элементы перерабатываются.</span><span class="sxs-lookup"><span data-stu-id="ebf48-120">When a person of interest is added to a data investigation, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="ebf48-121">Однако с течением времени в почтовый ящик пользователя или в учетную запись OneDrive можно добавить более частично индексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="ebf48-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="ebf48-122">При необходимости вы можете обновить индексы.</span><span class="sxs-lookup"><span data-stu-id="ebf48-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="ebf48-123">Обновление индексов людей — длительный процесс.</span><span class="sxs-lookup"><span data-stu-id="ebf48-123">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="ebf48-124">Рекомендуется не обновлять индексы более одного раза в течение одного дня при расследовании.</span><span class="sxs-lookup"><span data-stu-id="ebf48-124">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
