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
description: При добавлении хранителя в дело Advanced eDiscovery все содержимое, которое было признано частично индексируемым, повторно обработать, чтобы сделать его полностью искомым.
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750760"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="58237-103">Расширенная индексация данных хранителя</span><span class="sxs-lookup"><span data-stu-id="58237-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="58237-104">При добавлении хранителя в дело Advanced eDiscovery все содержимое, которое было признано частично индексируемым, повторно обработать, чтобы сделать его полностью искомым.</span><span class="sxs-lookup"><span data-stu-id="58237-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="58237-105">Этот процесс называется *"Расширенный индексация".*</span><span class="sxs-lookup"><span data-stu-id="58237-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="58237-106">Контент может быть частично индексироваться по ряду причин, включая наличие изображений, неподтверченные типы файлов или ограничения на размер индексации файлов.</span><span class="sxs-lookup"><span data-stu-id="58237-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="58237-107">Дополнительные информацию о поддержке обработки и частично индексных элементов см. в:</span><span class="sxs-lookup"><span data-stu-id="58237-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="58237-108">Поддерживаемые типы файлов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="58237-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="58237-109">Частично индексированные элементы в средстве "Поиск контента" в Office 365</span><span class="sxs-lookup"><span data-stu-id="58237-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="58237-110">Форматы файлов, индексируемые службой поиска Exchange</span><span class="sxs-lookup"><span data-stu-id="58237-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="58237-111">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="58237-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="58237-112">Просмотр результатов расширенных индексации</span><span class="sxs-lookup"><span data-stu-id="58237-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="58237-113">После завершения процесса advanced indexing можно получить представление об эффективности обработки.</span><span class="sxs-lookup"><span data-stu-id="58237-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="58237-114">В представлении результатов "Расширенный индексация" на вкладке "Обработка" для дела на графике перечислены элементы, добавленные в *гибридный индекс.* </span><span class="sxs-lookup"><span data-stu-id="58237-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="58237-115">Гибридный индекс — это место, где Advanced eDiscovery хранит повторно обобъещенное содержимое.</span><span class="sxs-lookup"><span data-stu-id="58237-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="58237-116">Это представление также включает количество элементов, которые требуют исправлений, и еще один график ошибок по типу файла.</span><span class="sxs-lookup"><span data-stu-id="58237-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="58237-117">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="58237-117">For more information, see:</span></span>

- [<span data-ttu-id="58237-118">Исправление ошибок при обработке данных</span><span class="sxs-lookup"><span data-stu-id="58237-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="58237-119">Исправление ошибки одного элемента</span><span class="sxs-lookup"><span data-stu-id="58237-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="58237-120">Обновление индекса Advanced для хранителей</span><span class="sxs-lookup"><span data-stu-id="58237-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="58237-121">При добавлении хранителя в дело Advanced eDiscovery все частично индексные элементы повторно обучаются.</span><span class="sxs-lookup"><span data-stu-id="58237-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="58237-122">Однако по мере того как время проходит, в почтовый ящик пользователя или учетную запись OneDrive могут добавляться частично индексные элементы.</span><span class="sxs-lookup"><span data-stu-id="58237-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="58237-123">При необходимости вы можете обновить индекс для определенного хранителя.</span><span class="sxs-lookup"><span data-stu-id="58237-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="58237-124">Дополнительные сведения см. в [поддомене "Управление хранителями" в деле Advanced eDiscovery.](manage-new-custodians.md#re-index-custodian-data)</span><span class="sxs-lookup"><span data-stu-id="58237-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="58237-125">Вы также можете обновить индекс для всех хранителей в случае, щелкнув индекс обновления **на** вкладке **"Обработка".**</span><span class="sxs-lookup"><span data-stu-id="58237-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="58237-126">Обновление индексов хранителя является длительным процессом.</span><span class="sxs-lookup"><span data-stu-id="58237-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="58237-127">Рекомендуется не обновлять индексы более одного раза в день.</span><span class="sxs-lookup"><span data-stu-id="58237-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>
