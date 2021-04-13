---
title: Запуск и настройка запланированных и по запросу сканов
description: Настройка и инициирование антивирусных сканов Microsoft Defender в конечных точках сети.
keywords: сканирование, расписание, настройка, исключения, исключение файлов, исправление, результаты проверки, карантин, удаление угрозы, быстрое сканирование, полное сканирование, антивирус Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8aa735cf7490a451a5758c3799bd08dff61f8063
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690799"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a><span data-ttu-id="b8c1d-104">Настройка, инициирование и проверка результатов проверки и устранения антивирусных программ Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b8c1d-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b8c1d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b8c1d-105">**Applies to:**</span></span>

- [<span data-ttu-id="b8c1d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b8c1d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b8c1d-107">Для настройки антивирусных сканов Microsoft Defender можно использовать инструменты групповой политики, PowerShell и Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="b8c1d-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="b8c1d-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b8c1d-108">In this section</span></span>

<span data-ttu-id="b8c1d-109">Статья</span><span class="sxs-lookup"><span data-stu-id="b8c1d-109">Topic</span></span> | <span data-ttu-id="b8c1d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b8c1d-110">Description</span></span>
---|---
[<span data-ttu-id="b8c1d-111">Настройка и проверка исключений файлов, папок и открытых процессом файлов в антивирусных проверках Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b8c1d-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="b8c1d-112">Можно исключить файлы (в том числе файлы, измененные заданными процессами) и папки из проверки по запросу, планового сканирования и мониторинга и сканирования защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="b8c1d-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span>
[<span data-ttu-id="b8c1d-113">Настройка параметров антивирусного сканирования Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b8c1d-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="b8c1d-114">Можно настроить антивирус Microsoft Defender, чтобы включить в сканирование определенные типы файлов хранения электронной почты, точек архивирования или репара и архивных файлов (например, файлов zip).</span><span class="sxs-lookup"><span data-stu-id="b8c1d-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="b8c1d-115">Вы также можете включить сканирование сетевых файлов</span><span class="sxs-lookup"><span data-stu-id="b8c1d-115">You can also enable network file scanning</span></span>
[<span data-ttu-id="b8c1d-116">Настройка исправлений для сканирования</span><span class="sxs-lookup"><span data-stu-id="b8c1d-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="b8c1d-117">Настройка того, что должен делать антивирус Microsoft Defender при обнаружении угрозы, и как долго должны храниться карантинные файлы в папке карантина</span><span class="sxs-lookup"><span data-stu-id="b8c1d-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span>
[<span data-ttu-id="b8c1d-118">Настройка запланированных сканов</span><span class="sxs-lookup"><span data-stu-id="b8c1d-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="b8c1d-119">Настройка повторяющихся (запланированных) сканирований, в том числе при их запуске и в качестве полного или быстрого сканирования.</span><span class="sxs-lookup"><span data-stu-id="b8c1d-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span>
[<span data-ttu-id="b8c1d-120">Настройка и запуск сканирования</span><span class="sxs-lookup"><span data-stu-id="b8c1d-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="b8c1d-121">Запуск и настройка сканирования по запросу с помощью PowerShell, инструментов управления Windows или отдельно на конечных точках с помощью приложения Безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="b8c1d-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span>
[<span data-ttu-id="b8c1d-122">Просмотр результатов сканирования</span><span class="sxs-lookup"><span data-stu-id="b8c1d-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="b8c1d-123">Просмотрите результаты сканирования с помощью Microsoft Endpoint Configuration Manager, Microsoft Intune или приложения безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="b8c1d-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span>