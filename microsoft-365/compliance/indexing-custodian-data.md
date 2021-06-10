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
description: Когда хранитель добавляется в Advanced eDiscovery, любое содержимое, которое было сочтено частично индексируемым, будет повторно реализовано, чтобы сделать его полностью поисковым.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911213"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="3f59d-103">Расширенная индексация данных хранителя</span><span class="sxs-lookup"><span data-stu-id="3f59d-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="3f59d-104">Когда хранитель добавляется в Advanced eDiscovery, любое содержимое, которое было сочтено частично индексируемым, будет повторно реализовано, чтобы сделать его полностью поисковым.</span><span class="sxs-lookup"><span data-stu-id="3f59d-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="3f59d-105">Этот процесс называется *Advanced indexing*.</span><span class="sxs-lookup"><span data-stu-id="3f59d-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="3f59d-106">Содержимое может быть частично индексироваться по ряду причин, включая наличие изображений, неподтверченных типов файлов или при индексации ограничений размера файла.</span><span class="sxs-lookup"><span data-stu-id="3f59d-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="3f59d-107">Дополнительные материалы о поддержке обработки и частично индексациях элементов см. в статьи:</span><span class="sxs-lookup"><span data-stu-id="3f59d-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="3f59d-108">Поддерживаемые типы файлов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3f59d-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="3f59d-109">Частично индексированные элементы в средстве "Поиск контента" в Office 365</span><span class="sxs-lookup"><span data-stu-id="3f59d-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="3f59d-110">Форматы файлов, индексируемые службой поиска Exchange</span><span class="sxs-lookup"><span data-stu-id="3f59d-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="3f59d-111">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="3f59d-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="3f59d-112">Просмотр результатов предварительной индексации</span><span class="sxs-lookup"><span data-stu-id="3f59d-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="3f59d-113">После завершения процесса предварительной индексации можно получить представление об эффективности обработки.</span><span class="sxs-lookup"><span data-stu-id="3f59d-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="3f59d-114">В представлении результатов предварительной индексации на вкладке **Обработка** для случая на графике перечислены количество элементов, добавленных в *гибридный индекс.*</span><span class="sxs-lookup"><span data-stu-id="3f59d-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="3f59d-115">Гибридный индекс — это Advanced eDiscovery, где хранится повторное содержимое.</span><span class="sxs-lookup"><span data-stu-id="3f59d-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="3f59d-116">Это представление также включает количество элементов, которые требуют исправлений, и еще один график ошибок по типу файла.</span><span class="sxs-lookup"><span data-stu-id="3f59d-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="3f59d-117">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="3f59d-117">For more information, see:</span></span>

- [<span data-ttu-id="3f59d-118">Исправление ошибок при обработке данных</span><span class="sxs-lookup"><span data-stu-id="3f59d-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="3f59d-119">Исправление ошибки одного элемента</span><span class="sxs-lookup"><span data-stu-id="3f59d-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="3f59d-120">Обновление индекса Advanced для хранителей</span><span class="sxs-lookup"><span data-stu-id="3f59d-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="3f59d-121">При добавлении хранителя в Advanced eDiscovery случае все частично индексные элементы будут повторно проиндексироваться.</span><span class="sxs-lookup"><span data-stu-id="3f59d-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="3f59d-122">Однако с течением времени в почтовый ящик или учетную запись пользователя может быть добавлено OneDrive элементов.</span><span class="sxs-lookup"><span data-stu-id="3f59d-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="3f59d-123">При необходимости можно обновить индекс для конкретного хранителя.</span><span class="sxs-lookup"><span data-stu-id="3f59d-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="3f59d-124">Дополнительные сведения см. в [статью Управление хранителями в Advanced eDiscovery случае](manage-new-custodians.md#re-index-custodian-data).</span><span class="sxs-lookup"><span data-stu-id="3f59d-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="3f59d-125">Вы также можете обновить индекс для всех хранителей в случае, щелкнув индекс **Обновления** на вкладке **Обработка.**</span><span class="sxs-lookup"><span data-stu-id="3f59d-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="3f59d-126">Обновление индексов хранителя — это длительный процесс.</span><span class="sxs-lookup"><span data-stu-id="3f59d-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="3f59d-127">Рекомендуется не обновлять индексы несколько раз в день.</span><span class="sxs-lookup"><span data-stu-id="3f59d-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>