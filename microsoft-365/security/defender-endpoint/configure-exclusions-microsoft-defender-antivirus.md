---
title: Настройка исключений для проверки антивируса Microsoft Defender
description: Вы можете исключить проверку файлов (в том числе файлов, измененных указанными процессами) и папок с помощью microsoft Defender AV. Проверка исключений с помощью PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 08f7f9d4a6e9e70d3ef071f30712b2ae53f4ea52
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764667"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="b9d6b-104">Настройка и проверка исключений для проверки антивирусных программ Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b9d6b-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b9d6b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b9d6b-105">**Applies to:**</span></span>

- [<span data-ttu-id="b9d6b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b9d6b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b9d6b-107">Некоторые файлы, папки, процессы и файлы, открытые процессом, можно исключить из антивирусных сканов Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="b9d6b-108">Такие исключения применяются к [запланированным](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [проверкам,](run-scan-microsoft-defender-antivirus.md)проверкам по запросу и постоянному контролю и защите в [режиме реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b9d6b-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b9d6b-109">Исключения для файлов, открытых процессом, применяются только к защите в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="b9d6b-110">Настройка и проверка исключений</span><span class="sxs-lookup"><span data-stu-id="b9d6b-110">Configure and validate exclusions</span></span>

<span data-ttu-id="b9d6b-111">Для настройки и проверки исключений см. следующие ниже.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="b9d6b-112">[Настройка и проверка исключений на основе имени файла, расширения и расположения папки.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b9d6b-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b9d6b-113">Это позволяет исключить файлы из антивирусных сканов Microsoft Defender в зависимости от их расширения, имени файла или расположения.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="b9d6b-114">[Настройка и проверка исключений для файлов, открытых процессами.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b9d6b-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b9d6b-115">Это позволяет исключить файлы из сканов, открытых определенным процессом.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="b9d6b-116">Рекомендации по определению исключений</span><span class="sxs-lookup"><span data-stu-id="b9d6b-116">Recommendations for defining exclusions</span></span>
[!IMPORTANT]
<span data-ttu-id="b9d6b-117">Антивирус Microsoft Defender включает множество автоматических исключений, основанных на известных действиях операционной системы и типичных файлах управления, например используемых в управлении предприятиями, управлении базами данных и других корпоративных сценариях и ситуациях.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
<span data-ttu-id="b9d6b-118">Определение исключений снижает защиту, предложенную антивирусом Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="b9d6b-119">Всегда следует оценивать риски, связанные с реализацией исключений, и следует исключить только те файлы, которые, как вы уверены, не являются вредоносными.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="b9d6b-120">Ниже приводится список рекомендаций, которые следует иметь в виду при определении исключений:</span><span class="sxs-lookup"><span data-stu-id="b9d6b-120">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="b9d6b-121">Исключения технически являются пробелом в защите— всегда следует учитывать дополнительные меры по смягчению последствий при определении исключений.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-121">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="b9d6b-122">Дополнительные меры по смягчению последствий могут быть так же простыми, как обеспечение того, чтобы исключенное расположение было надлежащим списком управления доступом (ACLs), политикой аудита, обрабатывалось с помощью программного обеспечения, соответствующего данным, и т.д.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-122">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="b9d6b-123">Периодически просматривайте исключения.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-123">Review the exclusions periodically.</span></span> <span data-ttu-id="b9d6b-124">Переосмотрите и повторно ввести меры по смягчению последствий в рамках процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-124">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="b9d6b-125">В идеале не следует определять упреждающие исключения.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-125">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="b9d6b-126">Например, не исключайте что-то только потому, что вы думаете, что это может быть проблемой в будущем.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-126">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="b9d6b-127">Используйте исключения только для определенных проблем, в основном в области производительности, а иногда и для совместимости приложений, которые могут смягчать исключения.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-127">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="b9d6b-128">Аудит изменений списка исключений.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-128">Audit the exclusion list changes.</span></span> <span data-ttu-id="b9d6b-129">Администратор службы безопасности должен сохранять достаточно контекста вокруг того, почему было добавлено определенное исключение.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-129">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="b9d6b-130">Вы должны иметь возможность дать ответ с конкретными рассуждениями о том, почему определенный путь был исключен.</span><span class="sxs-lookup"><span data-stu-id="b9d6b-130">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b9d6b-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b9d6b-131">Related articles</span></span>

- [<span data-ttu-id="b9d6b-132">Исключения антивируса Microsoft Defender на Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b9d6b-132">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b9d6b-133">Распространенные ошибки, которых следует избегать при определении исключений</span><span class="sxs-lookup"><span data-stu-id="b9d6b-133">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
