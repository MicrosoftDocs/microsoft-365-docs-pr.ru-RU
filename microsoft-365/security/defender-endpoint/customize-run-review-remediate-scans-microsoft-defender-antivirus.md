---
title: Запуск и настройка запланированных и по запросу сканов
description: Настройка и инициа антивирусная программа в Microsoft Defender проверки на конечных точках в сети.
keywords: сканирование, расписание, настройка, исключения, исключение файлов, исправление, результаты проверки, карантин, удаление угрозы, быстрое сканирование, полное сканирование, антивирусная программа в Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 31dbfa2ac6d5537f6d42c0bad612be5ef059368d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275280"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a><span data-ttu-id="3e16d-104">Настройка, инициирование и проверка результатов антивирусная программа в Microsoft Defender и исправлений</span><span class="sxs-lookup"><span data-stu-id="3e16d-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3e16d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3e16d-105">**Applies to:**</span></span>

- [<span data-ttu-id="3e16d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3e16d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3e16d-107">Для настройки антивирусная программа в Microsoft Defender можно использовать групповые политики, powerShell и Windows средства управления (WMI).</span><span class="sxs-lookup"><span data-stu-id="3e16d-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="3e16d-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3e16d-108">In this section</span></span>

<span data-ttu-id="3e16d-109">Статья</span><span class="sxs-lookup"><span data-stu-id="3e16d-109">Topic</span></span> | <span data-ttu-id="3e16d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3e16d-110">Description</span></span>
---|---
[<span data-ttu-id="3e16d-111">Настройка и проверка исключений файлов, папок и файлов, открытых процессом, в антивирусная программа в Microsoft Defender проверки</span><span class="sxs-lookup"><span data-stu-id="3e16d-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="3e16d-112">Можно исключить файлы (в том числе файлы, измененные заданными процессами) и папки из проверки по запросу, планового сканирования и мониторинга и сканирования защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="3e16d-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span>
[<span data-ttu-id="3e16d-113">Настройка параметров сканирования антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3e16d-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="3e16d-114">Вы можете настроить антивирусная программа в Microsoft Defender, чтобы включить в сканирование определенные типы файлов хранения электронной почты, точек архивирования или репаража, а также архивных файлов (например, .zip файлов).</span><span class="sxs-lookup"><span data-stu-id="3e16d-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="3e16d-115">Вы также можете включить сканирование сетевых файлов</span><span class="sxs-lookup"><span data-stu-id="3e16d-115">You can also enable network file scanning</span></span>
[<span data-ttu-id="3e16d-116">Настройка исправлений для сканирования</span><span class="sxs-lookup"><span data-stu-id="3e16d-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="3e16d-117">Настройка того, антивирусная программа в Microsoft Defender следует делать при обнаружении угрозы, и как долго должны храниться карантинные файлы в папке карантина</span><span class="sxs-lookup"><span data-stu-id="3e16d-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span>
[<span data-ttu-id="3e16d-118">Настройка запланированных сканов</span><span class="sxs-lookup"><span data-stu-id="3e16d-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="3e16d-119">Настройка повторяющихся (запланированных) сканирований, в том числе при их запуске и в качестве полного или быстрого сканирования.</span><span class="sxs-lookup"><span data-stu-id="3e16d-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span>
[<span data-ttu-id="3e16d-120">Настройка и запуск сканирования</span><span class="sxs-lookup"><span data-stu-id="3e16d-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="3e16d-121">Запуск и настройка сканирования по запросу с помощью PowerShell, Windows инструментов управления или отдельно на конечных точках с помощью Безопасность Windows приложения</span><span class="sxs-lookup"><span data-stu-id="3e16d-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span>
[<span data-ttu-id="3e16d-122">Просмотр результатов сканирования</span><span class="sxs-lookup"><span data-stu-id="3e16d-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="3e16d-123">Просмотр результатов сканирования с помощью Microsoft Endpoint Configuration Manager, Microsoft Intune или Безопасность Windows приложения</span><span class="sxs-lookup"><span data-stu-id="3e16d-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span>