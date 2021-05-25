---
title: Новые возможности в Microsoft Defender для конечной точки в Linux
description: Список основных изменений для Microsoft Defender для конечной точки на Linux.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, Whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0adcecefc19c681ef68498a3e7c375913d85985d
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651132"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="6b62b-104">Новые возможности в Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="6b62b-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a><span data-ttu-id="6b62b-105">101.29.64 (30.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="6b62b-105">101.29.64 (30.121042.12964.0)</span></span>

- <span data-ttu-id="6b62b-106">Начиная с этой версии, угрозы, обнаруженные во время проверки антивирусов по запросу, срабатываемой через клиент командной строки, автоматически устраняются.</span><span class="sxs-lookup"><span data-stu-id="6b62b-106">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="6b62b-107">Угрозы, обнаруженные во время сканирования, срабатываемого с помощью пользовательского интерфейса, по-прежнему требуют ручного действия.</span><span class="sxs-lookup"><span data-stu-id="6b62b-107">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="6b62b-108">`mdatp diagnostic real-time-protection-statistics` теперь поддерживает два дополнительных коммутатора:</span><span class="sxs-lookup"><span data-stu-id="6b62b-108">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="6b62b-109">`--sort`: сортирует выход, убывающий по общему количеству отсканированных файлов</span><span class="sxs-lookup"><span data-stu-id="6b62b-109">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="6b62b-110">`--top N`: отображает верхние результаты N (работает только в том `--sort` случае, если указано)</span><span class="sxs-lookup"><span data-stu-id="6b62b-110">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="6b62b-111">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="6b62b-111">Performance improvements & bug fixes</span></span>

## <a name="1012572-30121022125630"></a><span data-ttu-id="6b62b-112">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="6b62b-112">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="6b62b-113">Microsoft Defender для конечной точки на Linux теперь доступен в предварительном просмотре для государственных клиентов США.</span><span class="sxs-lookup"><span data-stu-id="6b62b-113">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="6b62b-114">Дополнительные сведения см. в [веб-сайте Microsoft Defender for Endpoint для государственных клиентов США.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="6b62b-114">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="6b62b-115">Исправлена проблема, из-за которой использование Microsoft Defender для конечной точки в Linux в системах с файлами FUSE привело к зависаю ОС</span><span class="sxs-lookup"><span data-stu-id="6b62b-115">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="6b62b-116">Улучшения производительности & других исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="6b62b-116">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="6b62b-117">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="6b62b-117">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="6b62b-118">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="6b62b-118">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="6b62b-119">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="6b62b-119">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="6b62b-120">Улучшение производительности для ситуации, когда в список исключений антивируса добавляется вся точка установки.</span><span class="sxs-lookup"><span data-stu-id="6b62b-120">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="6b62b-121">До этой версии файл, происходящий из точки установки, по-прежнему обрабатывался продуктом.</span><span class="sxs-lookup"><span data-stu-id="6b62b-121">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="6b62b-122">Начиная с этой версии, действие файлов для исключенных точек установки подавляется, что приводит к более производительности продукта.</span><span class="sxs-lookup"><span data-stu-id="6b62b-122">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="6b62b-123">Добавлен новый параметр в средство командной строки для просмотра сведений о последнем проверке по запросу.</span><span class="sxs-lookup"><span data-stu-id="6b62b-123">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="6b62b-124">Чтобы просмотреть сведения о последнем проверке по запросу, запустите `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="6b62b-124">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="6b62b-125">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="6b62b-125">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="6b62b-126">101.18.53</span><span class="sxs-lookup"><span data-stu-id="6b62b-126">101.18.53</span></span>

- <span data-ttu-id="6b62b-127">EDR Для Linux теперь [обычно доступны](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="6b62b-127">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="6b62b-128">Добавлен новый переключатель командной строки () для игнорирования исключений `--ignore-exclusions` av во время пользовательских сканирований ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="6b62b-128">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="6b62b-129">Расширенный `mdatp diagnostic create` с помощью нового параметра (), который позволяет сохранить журналы диагностики в другом `--path [directory]` каталоге</span><span class="sxs-lookup"><span data-stu-id="6b62b-129">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="6b62b-130">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="6b62b-130">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="6b62b-131">101.12.99</span><span class="sxs-lookup"><span data-stu-id="6b62b-131">101.12.99</span></span>

- <span data-ttu-id="6b62b-132">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="6b62b-132">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="6b62b-133">101.04.76</span><span class="sxs-lookup"><span data-stu-id="6b62b-133">101.04.76</span></span>

- <span data-ttu-id="6b62b-134">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="6b62b-134">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="6b62b-135">101.03.48</span><span class="sxs-lookup"><span data-stu-id="6b62b-135">101.03.48</span></span>

- <span data-ttu-id="6b62b-136">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="6b62b-136">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="6b62b-137">101.02.55</span><span class="sxs-lookup"><span data-stu-id="6b62b-137">101.02.55</span></span>

- <span data-ttu-id="6b62b-138">Исправлена проблема, из-за которой продукт иногда не начинается после перезагрузки или обновления</span><span class="sxs-lookup"><span data-stu-id="6b62b-138">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="6b62b-139">Исправлена проблема, из-за которой параметры прокси не сохраняются при обновлении продукта</span><span class="sxs-lookup"><span data-stu-id="6b62b-139">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="6b62b-140">101.00.75</span><span class="sxs-lookup"><span data-stu-id="6b62b-140">101.00.75</span></span>

- <span data-ttu-id="6b62b-141">Добавлена поддержка следующих типов файловой системы: `ecryptfs` , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` и `vfat`</span><span class="sxs-lookup"><span data-stu-id="6b62b-141">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="6b62b-142">Новый синтаксис для [средства командной строки.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="6b62b-142">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="6b62b-143">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="6b62b-143">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="6b62b-144">100.90.70</span><span class="sxs-lookup"><span data-stu-id="6b62b-144">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="6b62b-145">При обновлении установленного пакета из версии продукта до 100.90.70 обновление может привести к сбой в распространениях на основе red Hat и SLES.</span><span class="sxs-lookup"><span data-stu-id="6b62b-145">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="6b62b-146">Это из-за серьезного изменения пути файла.</span><span class="sxs-lookup"><span data-stu-id="6b62b-146">This is because of a major change in a file path.</span></span> <span data-ttu-id="6b62b-147">Временным решением является удаление старого пакета, а затем установка более нового пакета.</span><span class="sxs-lookup"><span data-stu-id="6b62b-147">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="6b62b-148">Эта проблема не существует в более новых версиях.</span><span class="sxs-lookup"><span data-stu-id="6b62b-148">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="6b62b-149">Исключения [антивирусов теперь поддерживают подкарды](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="6b62b-149">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="6b62b-150">Добавлена возможность [устранения проблем с производительностью](linux-support-perf.md) с помощью средства `mdatp` командной строки</span><span class="sxs-lookup"><span data-stu-id="6b62b-150">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="6b62b-151">Улучшения, чтобы сделать установку пакета более надежной</span><span class="sxs-lookup"><span data-stu-id="6b62b-151">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="6b62b-152">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="6b62b-152">Performance improvements & bug fixes</span></span>
