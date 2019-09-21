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
ms.openlocfilehash: ba85ef90570dfbf2228148bf5211a4b041a1cb61
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089457"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="1fe1e-102">Расширенная индексация данных хранителя</span><span class="sxs-lookup"><span data-stu-id="1fe1e-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="1fe1e-103">Когда хранитель добавляется к расширенному варианту обнаружения электронных данных, любое содержимое в Office 365, которое было признано частичным индексированием, повторно обрабатывается, чтобы сделать его полным поиском.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="1fe1e-104">Этот процесс называется *расширенной индексацией*.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="1fe1e-105">Контент может частично индексироваться по ряду причин, в том числе наличия изображений, неподдерживаемых типов файлов или при обнаружении ограничения на размер файлов индексирования.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="1fe1e-106">Дополнительные сведения о поддержке обработки в Office 365 и частично индексированных элементах приведены в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="1fe1e-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="1fe1e-107">Поддерживаемые типы файлов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1fe1e-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- [<span data-ttu-id="1fe1e-108">Частично индексированные элементы в средстве "Поиск контента" в Office 365</span><span class="sxs-lookup"><span data-stu-id="1fe1e-108">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
- [<span data-ttu-id="1fe1e-109">Форматы файлов, индексируемые службой поиска Exchange</span><span class="sxs-lookup"><span data-stu-id="1fe1e-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="1fe1e-110">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="1fe1e-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="1fe1e-111">Просмотр результатов расширенного индексирования</span><span class="sxs-lookup"><span data-stu-id="1fe1e-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="1fe1e-112">После выполнения расширенного процесса индексирования можно получить сведения о эффективности повторной обработки.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="1fe1e-113">В представлении индексирования хранитель на диаграмме перечислены все элементы, добавленные в *гибридный индекс*.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="1fe1e-114">Гибридный индекс — там, где Advanced eDiscovery сохраняет повторно обработанное содержимое.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="1fe1e-115">На диаграмме также представлено количество элементов, для которых требуется исправление, и еще один график ошибок по типам файлов.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="1fe1e-116">Дополнительные сведения см. в разделе [Устранение ошибок при обработке данных](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="1fe1e-116">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="1fe1e-117">Обновление расширенных индексов для custodians</span><span class="sxs-lookup"><span data-stu-id="1fe1e-117">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="1fe1e-118">Когда хранитель добавляется к расширенному варианту обнаружения электронных данных, все частично индексированные элементы обрабатываются повторно.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-118">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="1fe1e-119">Однако с течением времени в почтовый ящик пользователя или в учетную запись OneDrive можно добавить более частично индексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-119">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="1fe1e-120">При необходимости вы можете обновить индексы.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-120">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="1fe1e-121">Обновление индексов хранитель выполняется длительным процессом.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-121">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="1fe1e-122">Рекомендуется не обновлять индексы более одного раза в день.</span><span class="sxs-lookup"><span data-stu-id="1fe1e-122">It's recommended that you don't update indexes more than once per day in a case.</span></span>
