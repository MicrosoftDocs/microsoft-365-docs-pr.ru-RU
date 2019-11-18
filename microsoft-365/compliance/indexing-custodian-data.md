---
title: Расширенная индексация данных хранителя
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
description: ''
ms.openlocfilehash: a6259d839dd9a0ca196bae37afe374d1d8f21d53
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2019
ms.locfileid: "38687437"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="4ddb3-102">Расширенная индексация данных хранителя</span><span class="sxs-lookup"><span data-stu-id="4ddb3-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="4ddb3-103">Когда хранитель добавляется к расширенному варианту обнаружения электронных данных, любое содержимое в Office 365, которое было признано частичным индексированием, повторно обрабатывается, чтобы сделать его полным поиском.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="4ddb3-104">Этот процесс называется *расширенной индексацией*.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="4ddb3-105">Контент может частично индексироваться по ряду причин, в том числе наличия изображений, неподдерживаемых типов файлов или при обнаружении ограничения на размер файлов индексирования.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="4ddb3-106">Дополнительные сведения о поддержке обработки в Office 365 и частично индексированных элементах приведены в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="4ddb3-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="4ddb3-107">Поддерживаемые типы файлов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4ddb3-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- [<span data-ttu-id="4ddb3-108">Частично индексированные элементы в средстве "Поиск контента" в Office 365</span><span class="sxs-lookup"><span data-stu-id="4ddb3-108">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
- [<span data-ttu-id="4ddb3-109">Форматы файлов, индексируемые службой поиска Exchange</span><span class="sxs-lookup"><span data-stu-id="4ddb3-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="4ddb3-110">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="4ddb3-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="4ddb3-111">Просмотр результатов расширенного индексирования</span><span class="sxs-lookup"><span data-stu-id="4ddb3-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="4ddb3-112">После выполнения расширенного процесса индексирования можно получить сведения о эффективности повторной обработки.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="4ddb3-113">В представлении индексирования хранитель на диаграмме перечислены все элементы, добавленные в *гибридный индекс*.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="4ddb3-114">Гибридный индекс — там, где Advanced eDiscovery сохраняет повторно обработанное содержимое.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="4ddb3-115">На диаграмме также представлено количество элементов, для которых требуется исправление, и еще один график ошибок по типам файлов.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="4ddb3-116">Подробнее:</span><span class="sxs-lookup"><span data-stu-id="4ddb3-116">For more information, see:</span></span>

- [<span data-ttu-id="4ddb3-117">Исправление ошибок при обработке данных</span><span class="sxs-lookup"><span data-stu-id="4ddb3-117">Error remediation when processing data</span></span>](error-remediation.md)
- [<span data-ttu-id="4ddb3-118">Исправление ошибки одного элемента</span><span class="sxs-lookup"><span data-stu-id="4ddb3-118">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="4ddb3-119">Обновление расширенных индексов для custodians</span><span class="sxs-lookup"><span data-stu-id="4ddb3-119">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="4ddb3-120">Когда хранитель добавляется к расширенному варианту обнаружения электронных данных, все частично индексированные элементы обрабатываются повторно.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-120">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="4ddb3-121">Однако с течением времени в почтовый ящик пользователя или в учетную запись OneDrive можно добавить более частично индексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="4ddb3-122">При необходимости вы можете обновить индексы.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="4ddb3-123">Обновление индексов хранитель выполняется длительным процессом.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-123">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="4ddb3-124">Рекомендуется не обновлять индексы более одного раза в день.</span><span class="sxs-lookup"><span data-stu-id="4ddb3-124">It's recommended that you don't update indexes more than once per day in a case.</span></span>
