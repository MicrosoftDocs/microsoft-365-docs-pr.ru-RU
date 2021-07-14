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
ms.openlocfilehash: f510b7e9c0fa2c5c181709c96907610066a4b1cf
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430517"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="33cff-103">Расширенная индексация данных хранителя</span><span class="sxs-lookup"><span data-stu-id="33cff-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="33cff-104">Когда хранитель добавляется в Advanced eDiscovery, любое содержимое, которое было признано частично индексируемым или с ошибками индексирования, повторно передается для полного поиска.</span><span class="sxs-lookup"><span data-stu-id="33cff-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed or had indexing errors with is reindexed to make it fully searchable.</span></span>  <span data-ttu-id="33cff-105">Этот процесс реиндексации называется *Advanced indexing*.</span><span class="sxs-lookup"><span data-stu-id="33cff-105">This reindexing process is called *Advanced indexing*.</span></span> <span data-ttu-id="33cff-106">Существует ряд причин частичной индексации контента или ошибок индексирования.</span><span class="sxs-lookup"><span data-stu-id="33cff-106">There are a number of reasons that content is partially indexed or has indexing errors.</span></span> <span data-ttu-id="33cff-107">Это включает в себя файлы изображений или наличие изображений в файле, неподтверченные типы файлов или ограничения индексации файлов в размерах.</span><span class="sxs-lookup"><span data-stu-id="33cff-107">This includes image files or the presence of images in a file, unsupported file types, or file sized indexing limits.</span></span> <span data-ttu-id="33cff-108">Для SharePoint файлы расширенный индексация выполняется только для элементов, помеченных как частично индексированы или имеют ошибки индексирования.</span><span class="sxs-lookup"><span data-stu-id="33cff-108">For SharePoint files, Advanced indexing only runs on items are marked as partially indexed or that have indexing errors.</span></span> <span data-ttu-id="33cff-109">В Exchange сообщения электронной почты с вложениями изображений не помечены как частично индексированы или с ошибками индексирования.</span><span class="sxs-lookup"><span data-stu-id="33cff-109">In Exchange, email messages that have image attachments are not marked as partially indexed or with indexing errors.</span></span> <span data-ttu-id="33cff-110">Это означает, что эти файлы не будут реиндексироваться с помощью процесса индексации Advanced.</span><span class="sxs-lookup"><span data-stu-id="33cff-110">This means that those files will not be reindexed by Advanced indexing process.</span></span>

<span data-ttu-id="33cff-111">Дополнительные материалы о поддержке обработки и частично индексациях элементов см. в статьи:</span><span class="sxs-lookup"><span data-stu-id="33cff-111">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="33cff-112">Поддерживаемые типы файлов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="33cff-112">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="33cff-113">Частично индексированные элементы в средстве "Поиск контента" в Office 365</span><span class="sxs-lookup"><span data-stu-id="33cff-113">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="33cff-114">Форматы файлов, индексируемые службой поиска Exchange</span><span class="sxs-lookup"><span data-stu-id="33cff-114">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="33cff-115">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="33cff-115">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="33cff-116">Просмотр результатов предварительной индексации</span><span class="sxs-lookup"><span data-stu-id="33cff-116">Viewing Advanced indexing results</span></span>

<span data-ttu-id="33cff-117">После завершения процесса предварительной индексации можно получить представление об эффективности обработки.</span><span class="sxs-lookup"><span data-stu-id="33cff-117">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="33cff-118">В представлении результатов предварительной индексации на вкладке **Обработка** для случая на графике перечислены количество элементов, добавленных в *гибридный индекс.*</span><span class="sxs-lookup"><span data-stu-id="33cff-118">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="33cff-119">Гибридный индекс — это Advanced eDiscovery, где хранится повторное содержимое.</span><span class="sxs-lookup"><span data-stu-id="33cff-119">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="33cff-120">Это представление также включает количество элементов, которые требуют исправлений, и еще один график ошибок по типу файла.</span><span class="sxs-lookup"><span data-stu-id="33cff-120">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="33cff-121">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="33cff-121">For more information, see:</span></span>

- [<span data-ttu-id="33cff-122">Исправление ошибок при обработке данных</span><span class="sxs-lookup"><span data-stu-id="33cff-122">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="33cff-123">Исправление ошибки одного элемента</span><span class="sxs-lookup"><span data-stu-id="33cff-123">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="33cff-124">Обновление индекса Advanced для хранителей</span><span class="sxs-lookup"><span data-stu-id="33cff-124">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="33cff-125">При добавлении хранителя в Advanced eDiscovery случае все частично индексные элементы будут повторно проиндексироваться.</span><span class="sxs-lookup"><span data-stu-id="33cff-125">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="33cff-126">Однако с течением времени в почтовый ящик или учетную запись пользователя может быть добавлено OneDrive элементов.</span><span class="sxs-lookup"><span data-stu-id="33cff-126">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="33cff-127">При необходимости можно обновить индекс для конкретного хранителя.</span><span class="sxs-lookup"><span data-stu-id="33cff-127">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="33cff-128">Дополнительные сведения см. в [статью Управление хранителями в Advanced eDiscovery случае](manage-new-custodians.md#re-index-custodian-data).</span><span class="sxs-lookup"><span data-stu-id="33cff-128">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="33cff-129">Вы также можете обновить индекс для всех хранителей в случае, щелкнув индекс **Обновления** на вкладке **Обработка.**</span><span class="sxs-lookup"><span data-stu-id="33cff-129">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="33cff-130">Обновление индексов хранителя — это длительный процесс.</span><span class="sxs-lookup"><span data-stu-id="33cff-130">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="33cff-131">Рекомендуется не обновлять индексы несколько раз в день.</span><span class="sxs-lookup"><span data-stu-id="33cff-131">It's recommended that you don't update indexes more than once a day in a case.</span></span>
