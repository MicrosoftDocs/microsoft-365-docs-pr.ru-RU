---
title: Настройка исключений для проверки av Microsoft Defender
description: Вы можете исключить проверку файлов (в том числе файлов, измененных указанными процессами) и папок с помощью microsoft Defender AV. Проверка исключений с помощью PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691506"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="b6a6e-104">Настройка и проверка исключений для проверки антивирусных программ Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b6a6e-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b6a6e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b6a6e-105">**Applies to:**</span></span>

- [<span data-ttu-id="b6a6e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b6a6e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b6a6e-107">Некоторые файлы, папки, процессы и файлы, открытые процессом, можно исключить из антивирусных сканов Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="b6a6e-108">Такие исключения применяются к [запланированным](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [проверкам,](run-scan-microsoft-defender-antivirus.md)проверкам по запросу и постоянному контролю и защите в [режиме реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b6a6e-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b6a6e-109">Исключения для файлов, открытых процессом, применяются только к защите в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="b6a6e-110">Настройка и проверка исключений</span><span class="sxs-lookup"><span data-stu-id="b6a6e-110">Configure and validate exclusions</span></span>

<span data-ttu-id="b6a6e-111">Для настройки и проверки исключений см. следующие ниже.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="b6a6e-112">[Настройка и проверка исключений на основе имени файла, расширения и расположения папки.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b6a6e-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b6a6e-113">Это позволяет исключить файлы из антивирусных сканов Microsoft Defender в зависимости от их расширения, имени файла или расположения.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="b6a6e-114">[Настройка и проверка исключений для файлов, открытых процессами.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b6a6e-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b6a6e-115">Это позволяет исключить файлы из сканов, открытых определенным процессом.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="b6a6e-116">Рекомендации по определению исключений</span><span class="sxs-lookup"><span data-stu-id="b6a6e-116">Recommendations for defining exclusions</span></span>

<span data-ttu-id="b6a6e-117">Определение исключений снижает защиту, предложенную антивирусом Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-117">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="b6a6e-118">Всегда следует оценивать риски, связанные с реализацией исключений, и следует исключить только те файлы, которые, как вы уверены, не являются вредоносными.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="b6a6e-119">Ниже приводится список рекомендаций, которые следует иметь в виду при определении исключений:</span><span class="sxs-lookup"><span data-stu-id="b6a6e-119">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="b6a6e-120">Исключения технически являются пробелом в защите— всегда следует учитывать дополнительные меры по смягчению последствий при определении исключений.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-120">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="b6a6e-121">Дополнительные меры по смягчению последствий могут быть так же простыми, как обеспечение того, чтобы исключенное расположение было надлежащим списком управления доступом (ACLs), политикой аудита, обрабатывалось с помощью программного обеспечения, соответствующего данным, и т.д.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-121">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="b6a6e-122">Периодически просматривайте исключения.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-122">Review the exclusions periodically.</span></span> <span data-ttu-id="b6a6e-123">Переосмотрите и повторно ввести меры по смягчению последствий в рамках процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-123">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="b6a6e-124">В идеале не следует определять упреждающие исключения.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-124">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="b6a6e-125">Например, не исключайте что-то только потому, что вы думаете, что это может быть проблемой в будущем.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-125">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="b6a6e-126">Используйте исключения только для определенных проблем, в основном в области производительности, а иногда и для совместимости приложений, которые могут смягчать исключения.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-126">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="b6a6e-127">Аудит изменений списка исключений.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-127">Audit the exclusion list changes.</span></span> <span data-ttu-id="b6a6e-128">Администратор службы безопасности должен сохранять достаточно контекста вокруг того, почему было добавлено определенное исключение.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-128">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="b6a6e-129">Вы должны иметь возможность дать ответ с конкретными рассуждениями о том, почему определенный путь был исключен.</span><span class="sxs-lookup"><span data-stu-id="b6a6e-129">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b6a6e-130">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b6a6e-130">Related articles</span></span>

- [<span data-ttu-id="b6a6e-131">Исключения антивируса Microsoft Defender на Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b6a6e-131">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b6a6e-132">Распространенные ошибки, которые следует избегать при определении исключений</span><span class="sxs-lookup"><span data-stu-id="b6a6e-132">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)