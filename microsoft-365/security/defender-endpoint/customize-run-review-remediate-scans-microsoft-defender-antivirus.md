---
title: Запуск и настройка запланированных и по запросу сканов
description: Настройка и инициирование антивирусных сканов Microsoft Defender в конечных точках сети.
keywords: сканирование, расписание, настройка, исключения, исключение файлов, исправление, результаты проверки, карантин, удаление угрозы, быстрое сканирование, полное сканирование, антивирус Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 115a8ee56ca5e9768b3aba11c37f8423ef31a67b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765699"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a><span data-ttu-id="2353e-104">Настройка, инициирование и проверка результатов проверки и устранения антивирусных программ Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2353e-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2353e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2353e-105">**Applies to:**</span></span>

- [<span data-ttu-id="2353e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="2353e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2353e-107">Для настройки антивирусных сканов Microsoft Defender можно использовать инструменты групповой политики, PowerShell и Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="2353e-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="2353e-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2353e-108">In this section</span></span>

<span data-ttu-id="2353e-109">Статья</span><span class="sxs-lookup"><span data-stu-id="2353e-109">Topic</span></span> | <span data-ttu-id="2353e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2353e-110">Description</span></span>
---|---
[<span data-ttu-id="2353e-111">Настройка и проверка исключений файлов, папок и открытых процессом файлов в антивирусных проверках Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2353e-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="2353e-112">Можно исключить файлы (в том числе файлы, измененные заданными процессами) и папки из проверки по запросу, планового сканирования и мониторинга и сканирования защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="2353e-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span>
[<span data-ttu-id="2353e-113">Настройка параметров сканирования антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2353e-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="2353e-114">Можно настроить антивирус Microsoft Defender, чтобы включить в сканирование определенные типы файлов хранения электронной почты, точек архивирования или репара и архивных файлов (например, файлов zip).</span><span class="sxs-lookup"><span data-stu-id="2353e-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="2353e-115">Вы также можете включить сканирование сетевых файлов</span><span class="sxs-lookup"><span data-stu-id="2353e-115">You can also enable network file scanning</span></span>
[<span data-ttu-id="2353e-116">Настройка исправлений для сканирования</span><span class="sxs-lookup"><span data-stu-id="2353e-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="2353e-117">Настройка того, что должен делать антивирус Microsoft Defender при обнаружении угрозы, и как долго должны храниться карантинные файлы в папке карантина</span><span class="sxs-lookup"><span data-stu-id="2353e-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span>
[<span data-ttu-id="2353e-118">Настройка запланированных сканов</span><span class="sxs-lookup"><span data-stu-id="2353e-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="2353e-119">Настройка повторяющихся (запланированных) сканирований, в том числе при их запуске и в качестве полного или быстрого сканирования.</span><span class="sxs-lookup"><span data-stu-id="2353e-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span>
[<span data-ttu-id="2353e-120">Настройка и запуск сканирования</span><span class="sxs-lookup"><span data-stu-id="2353e-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="2353e-121">Запуск и настройка сканирования по запросу с помощью PowerShell, инструментов управления Windows или отдельно на конечных точках с помощью приложения Безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="2353e-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span>
[<span data-ttu-id="2353e-122">Просмотр результатов сканирования</span><span class="sxs-lookup"><span data-stu-id="2353e-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="2353e-123">Просмотрите результаты сканирования с помощью Microsoft Endpoint Configuration Manager, Microsoft Intune или приложения безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="2353e-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span>