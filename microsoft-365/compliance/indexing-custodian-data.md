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
description: При добавлении хранителя в дело advanced eDiscovery любое содержимое, которое было признано частично индексируемым, повторно передается для полного поиска.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911213"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="fa8c2-103">Расширенная индексация данных хранителя</span><span class="sxs-lookup"><span data-stu-id="fa8c2-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="fa8c2-104">При добавлении хранителя в дело advanced eDiscovery любое содержимое, которое было признано частично индексируемым, повторно передается для полного поиска.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="fa8c2-105">Этот процесс называется *Advanced indexing*.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="fa8c2-106">Содержимое может быть частично индексироваться по ряду причин, включая наличие изображений, неподтверченных типов файлов или при индексации ограничений размера файла.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="fa8c2-107">Дополнительные материалы о поддержке обработки и частично индексациях элементов см. в статьи:</span><span class="sxs-lookup"><span data-stu-id="fa8c2-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="fa8c2-108">Поддерживаемые типы файлов в advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fa8c2-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="fa8c2-109">Частично индексированные элементы в средстве "Поиск контента" в Office 365</span><span class="sxs-lookup"><span data-stu-id="fa8c2-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="fa8c2-110">Форматы файлов, индексируемые службой поиска Exchange</span><span class="sxs-lookup"><span data-stu-id="fa8c2-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="fa8c2-111">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="fa8c2-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="fa8c2-112">Просмотр результатов предварительной индексации</span><span class="sxs-lookup"><span data-stu-id="fa8c2-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="fa8c2-113">После завершения процесса предварительной индексации можно получить представление об эффективности обработки.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="fa8c2-114">В представлении результатов предварительной индексации на вкладке **Обработка** для случая на графике перечислены количество элементов, добавленных в *гибридный индекс.*</span><span class="sxs-lookup"><span data-stu-id="fa8c2-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="fa8c2-115">Гибридный индекс — это место, где advanced eDiscovery хранит повторное содержимое.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="fa8c2-116">Это представление также включает количество элементов, которые требуют исправлений, и еще один график ошибок по типу файла.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="fa8c2-117">Дополнительные сведения см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="fa8c2-117">For more information, see:</span></span>

- [<span data-ttu-id="fa8c2-118">Исправление ошибок при обработке данных</span><span class="sxs-lookup"><span data-stu-id="fa8c2-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="fa8c2-119">Исправление ошибки одного элемента</span><span class="sxs-lookup"><span data-stu-id="fa8c2-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="fa8c2-120">Обновление индекса Advanced для хранителей</span><span class="sxs-lookup"><span data-stu-id="fa8c2-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="fa8c2-121">При добавлении хранителя в дело advanced eDiscovery все частично индексные элементы будут повторно проиндексироваться.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="fa8c2-122">Однако со временем в почтовый ящик пользователя или учетную запись OneDrive могут быть добавлены более частично индексные элементы.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="fa8c2-123">При необходимости можно обновить индекс для конкретного хранителя.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="fa8c2-124">Дополнительные сведения см. в [примере Управление хранителями в деле advanced eDiscovery.](manage-new-custodians.md#re-index-custodian-data)</span><span class="sxs-lookup"><span data-stu-id="fa8c2-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="fa8c2-125">Вы также можете обновить индекс для всех хранителей в случае, щелкнув индекс **Обновления** на вкладке **Обработка.**</span><span class="sxs-lookup"><span data-stu-id="fa8c2-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="fa8c2-126">Обновление индексов хранителя — это длительный процесс.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="fa8c2-127">Рекомендуется не обновлять индексы несколько раз в день.</span><span class="sxs-lookup"><span data-stu-id="fa8c2-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>