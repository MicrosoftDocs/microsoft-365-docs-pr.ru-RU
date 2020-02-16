---
title: Расширенная индексация данных хранителя
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
description: Когда хранитель добавляется к расширенному варианту обнаружения электронных данных, любое содержимое в Office 365, которое было признано частичным индексированием, повторно обрабатывается, чтобы сделать его полным поиском.
ms.openlocfilehash: 3c1bead5f853a39410a6a018f170ee637dfcf84e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072896"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="fa881-103">Расширенная индексация данных хранителя</span><span class="sxs-lookup"><span data-stu-id="fa881-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="fa881-104">Когда хранитель добавляется к расширенному варианту обнаружения электронных данных, любое содержимое в Office 365, которое было признано частичным индексированием, повторно обрабатывается, чтобы сделать его полным поиском.</span><span class="sxs-lookup"><span data-stu-id="fa881-104">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="fa881-105">Этот процесс называется *расширенной индексацией*.</span><span class="sxs-lookup"><span data-stu-id="fa881-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="fa881-106">Контент может частично индексироваться по ряду причин, в том числе наличия изображений, неподдерживаемых типов файлов или при обнаружении ограничения на размер файлов индексирования.</span><span class="sxs-lookup"><span data-stu-id="fa881-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="fa881-107">Дополнительные сведения о поддержке обработки в Office 365 и частично индексированных элементах приведены в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="fa881-107">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="fa881-108">Поддерживаемые типы файлов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fa881-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="fa881-109">Частично индексированные элементы в средстве "Поиск контента" в Office 365</span><span class="sxs-lookup"><span data-stu-id="fa881-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="fa881-110">Форматы файлов, индексируемые службой поиска Exchange</span><span class="sxs-lookup"><span data-stu-id="fa881-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="fa881-111">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="fa881-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="fa881-112">Просмотр результатов расширенного индексирования</span><span class="sxs-lookup"><span data-stu-id="fa881-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="fa881-113">После выполнения расширенного процесса индексирования можно получить сведения о эффективности повторной обработки.</span><span class="sxs-lookup"><span data-stu-id="fa881-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="fa881-114">В представлении "расширенные результаты индексирования" на вкладке " **Обработка** " для случая в диаграмме отображается количество элементов, добавленных в *гибридный индекс*.</span><span class="sxs-lookup"><span data-stu-id="fa881-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="fa881-115">Гибридный индекс — там, где Advanced eDiscovery сохраняет повторно обработанное содержимое.</span><span class="sxs-lookup"><span data-stu-id="fa881-115">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="fa881-116">Это представление также включает количество элементов, для которых требуется исправление, и другой график ошибок по типам файлов.</span><span class="sxs-lookup"><span data-stu-id="fa881-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="fa881-117">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="fa881-117">For more information, see:</span></span>

- [<span data-ttu-id="fa881-118">Исправление ошибок при обработке данных</span><span class="sxs-lookup"><span data-stu-id="fa881-118">Error remediation when processing data</span></span>](error-remediation.md)

- [<span data-ttu-id="fa881-119">Исправление ошибки одного элемента</span><span class="sxs-lookup"><span data-stu-id="fa881-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="fa881-120">Обновление расширенного индекса для custodians</span><span class="sxs-lookup"><span data-stu-id="fa881-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="fa881-121">Когда хранитель добавляется к расширенному варианту обнаружения электронных данных, все частично индексированные элементы обрабатываются повторно.</span><span class="sxs-lookup"><span data-stu-id="fa881-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="fa881-122">Однако с течением времени в почтовый ящик пользователя или в учетную запись OneDrive можно добавить более частично индексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="fa881-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="fa881-123">При необходимости вы можете обновить индекс для определенных хранитель.</span><span class="sxs-lookup"><span data-stu-id="fa881-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="fa881-124">Дополнительные сведения: [Управление custodians в расширенном случае обнаружения электронных](manage-new-custodians.md#re-index-custodian-data)данных.</span><span class="sxs-lookup"><span data-stu-id="fa881-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="fa881-125">Вы также можете обновить индекс для всех custodians в случае, щелкнув **индекс обновления** на вкладке **Обработка** .</span><span class="sxs-lookup"><span data-stu-id="fa881-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="fa881-126">Обновление индексов хранитель выполняется длительным процессом.</span><span class="sxs-lookup"><span data-stu-id="fa881-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="fa881-127">Рекомендуется не обновлять индексы более одного раза в день.</span><span class="sxs-lookup"><span data-stu-id="fa881-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>
