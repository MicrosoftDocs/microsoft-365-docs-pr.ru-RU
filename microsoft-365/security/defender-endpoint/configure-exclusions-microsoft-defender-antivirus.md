---
title: Настройка исключений для антивирусная программа в Microsoft Defender сканирования
description: Вы можете исключить проверку файлов (в том числе файлов, измененных указанными процессами) и папок антивирусная программа в Microsoft Defender. Проверка исключений с помощью PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275124"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="afdec-104">Настройка и проверка исключений для антивирусная программа в Microsoft Defender сканирования</span><span class="sxs-lookup"><span data-stu-id="afdec-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="afdec-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="afdec-105">**Applies to:**</span></span>

- [<span data-ttu-id="afdec-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="afdec-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="afdec-107">Некоторые файлы, папки, процессы и открытые процессом файлы можно исключить из антивирусная программа в Microsoft Defender сканирования.</span><span class="sxs-lookup"><span data-stu-id="afdec-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="afdec-108">Такие исключения применяются к [запланированным](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [проверкам,](run-scan-microsoft-defender-antivirus.md)проверкам по запросу и постоянному контролю и защите в [режиме реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="afdec-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="afdec-109">Исключения для файлов, открытых процессом, применяются только к защите в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="afdec-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="afdec-110">Настройка и проверка исключений</span><span class="sxs-lookup"><span data-stu-id="afdec-110">Configure and validate exclusions</span></span>

<span data-ttu-id="afdec-111">Для настройки и проверки исключений см. следующие ниже.</span><span class="sxs-lookup"><span data-stu-id="afdec-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="afdec-112">[Настройка и проверка исключений на основе имени файла, расширения и расположения папки.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="afdec-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="afdec-113">Можно исключить файлы из антивирусная программа в Microsoft Defender в зависимости от их расширения, имени файла или расположения.</span><span class="sxs-lookup"><span data-stu-id="afdec-113">You can exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="afdec-114">[Настройка и проверка исключений для файлов, открытых процессами.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="afdec-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="afdec-115">Вы можете исключить файлы из сканов, открытых определенным процессом.</span><span class="sxs-lookup"><span data-stu-id="afdec-115">You can exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="afdec-116">Рекомендации для определения исключений</span><span class="sxs-lookup"><span data-stu-id="afdec-116">Recommendations for defining exclusions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afdec-117">антивирусная программа в Microsoft Defender включает множество автоматических исключений, основанных на известных действиях операционной системы и типичных файлах управления, например используемых в управлении предприятиями, управлении базами данных и других корпоративных сценариях и ситуациях.</span><span class="sxs-lookup"><span data-stu-id="afdec-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
> 
> <span data-ttu-id="afdec-118">Определение исключений снижает защиту, предложенную антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="afdec-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="afdec-119">Всегда следует оценивать риски, связанные с реализацией исключений, и следует исключить только те файлы, которые, как вы уверены, не являются вредоносными.</span><span class="sxs-lookup"><span data-stu-id="afdec-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="afdec-120">При определении исключений следует помнить о следующих моментах:</span><span class="sxs-lookup"><span data-stu-id="afdec-120">Keep the following points in mind when you are defining exclusions:</span></span>  

- <span data-ttu-id="afdec-121">Исключения технически являются пробелом в защите.</span><span class="sxs-lookup"><span data-stu-id="afdec-121">Exclusions are technically a protection gap.</span></span> <span data-ttu-id="afdec-122">Всегда учитывайте смягчение при определении исключений.</span><span class="sxs-lookup"><span data-stu-id="afdec-122">Always consider mitigations when defining exclusions.</span></span> <span data-ttu-id="afdec-123">Другие меры по смягчению последствий могут быть так же просты, как убедиться, что исключенное расположение имеет соответствующие списки управления доступом (ACLs), политику аудита, обрабатывается с помощью обновления программного обеспечения и т.д.</span><span class="sxs-lookup"><span data-stu-id="afdec-123">Other mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="afdec-124">Периодически просматривайте исключения.</span><span class="sxs-lookup"><span data-stu-id="afdec-124">Review the exclusions periodically.</span></span> <span data-ttu-id="afdec-125">Перепроверка и повторное выполнение смягчения последствий в рамках процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="afdec-125">Recheck and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="afdec-126">В идеале избегайте определения исключений, которые должны быть активными.</span><span class="sxs-lookup"><span data-stu-id="afdec-126">Ideally, avoid defining exclusions intending to be proactive.</span></span> <span data-ttu-id="afdec-127">Например, не исключайте что-то только потому, что вы думаете, что это может быть проблемой в будущем.</span><span class="sxs-lookup"><span data-stu-id="afdec-127">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="afdec-128">Используйте исключения только для определенных проблем, например, связанных с производительностью или совместимостью приложений, которые могут смягчить исключения.</span><span class="sxs-lookup"><span data-stu-id="afdec-128">Use exclusions only for specific issues, such as those pertaining to performance or application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="afdec-129">Аудит изменений списка исключений.</span><span class="sxs-lookup"><span data-stu-id="afdec-129">Audit the exclusion list changes.</span></span> <span data-ttu-id="afdec-130">Администратор службы безопасности должен сохранять достаточно контекста вокруг того, почему было добавлено определенное исключение.</span><span class="sxs-lookup"><span data-stu-id="afdec-130">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="afdec-131">Вы должны иметь возможность дать ответ с конкретными рассуждениями о том, почему определенный путь был исключен.</span><span class="sxs-lookup"><span data-stu-id="afdec-131">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="afdec-132">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="afdec-132">Related articles</span></span>

- [<span data-ttu-id="afdec-133">антивирусная программа в Microsoft Defender исключений на Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="afdec-133">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="afdec-134">Распространенные ошибки, которых следует избегать при определении исключений</span><span class="sxs-lookup"><span data-stu-id="afdec-134">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
