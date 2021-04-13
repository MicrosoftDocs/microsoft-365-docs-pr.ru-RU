---
title: Новые возможности в Microsoft Defender для конечной точки в Linux
description: Список основных изменений для ATP Защитника Microsoft на Linux.
keywords: Microsoft, defender, atp, Linux, Whatsnew, release
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
ms.openlocfilehash: 2866cd0c9ee9b40aa9c08c4ff7dce64f745d3d03
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688637"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="3c262-104">Новые возможности в Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="3c262-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a><span data-ttu-id="3c262-105">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="3c262-105">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="3c262-106">Microsoft Defender для конечной точки на Linux теперь доступен в предварительном просмотре для государственных клиентов США.</span><span class="sxs-lookup"><span data-stu-id="3c262-106">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="3c262-107">Дополнительные сведения см. в [веб-сайте Microsoft Defender for Endpoint для государственных клиентов США.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="3c262-107">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="3c262-108">Исправлена проблема, из-за которой использование Microsoft Defender для конечной точки в Linux в системах с файлами FUSE привело к зависаю ОС</span><span class="sxs-lookup"><span data-stu-id="3c262-108">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="3c262-109">Улучшения производительности & других исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3c262-109">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="3c262-110">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="3c262-110">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="3c262-111">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3c262-111">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="3c262-112">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="3c262-112">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="3c262-113">Улучшение производительности для ситуации, когда в список исключений антивируса добавляется вся точка установки.</span><span class="sxs-lookup"><span data-stu-id="3c262-113">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="3c262-114">До этой версии файл, происходящий из точки установки, по-прежнему обрабатывался продуктом.</span><span class="sxs-lookup"><span data-stu-id="3c262-114">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="3c262-115">Начиная с этой версии, действие файлов для исключенных точек установки подавляется, что приводит к более производительности продукта.</span><span class="sxs-lookup"><span data-stu-id="3c262-115">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="3c262-116">Добавлен новый параметр в средство командной строки для просмотра сведений о последнем проверке по запросу.</span><span class="sxs-lookup"><span data-stu-id="3c262-116">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="3c262-117">Чтобы просмотреть сведения о последнем проверке по запросу, запустите `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="3c262-117">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="3c262-118">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3c262-118">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="3c262-119">101.18.53</span><span class="sxs-lookup"><span data-stu-id="3c262-119">101.18.53</span></span>

- <span data-ttu-id="3c262-120">EDR для Linux теперь [общедоступна](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="3c262-120">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="3c262-121">Добавлен новый переключатель командной строки () для игнорирования исключений `--ignore-exclusions` av во время пользовательских сканирований ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="3c262-121">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="3c262-122">Расширенный `mdatp diagnostic create` с помощью нового параметра (), который позволяет сохранить журналы диагностики в другом `--path [directory]` каталоге</span><span class="sxs-lookup"><span data-stu-id="3c262-122">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="3c262-123">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3c262-123">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="3c262-124">101.12.99</span><span class="sxs-lookup"><span data-stu-id="3c262-124">101.12.99</span></span>

- <span data-ttu-id="3c262-125">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3c262-125">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="3c262-126">101.04.76</span><span class="sxs-lookup"><span data-stu-id="3c262-126">101.04.76</span></span>

- <span data-ttu-id="3c262-127">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="3c262-127">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="3c262-128">101.03.48</span><span class="sxs-lookup"><span data-stu-id="3c262-128">101.03.48</span></span>

- <span data-ttu-id="3c262-129">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="3c262-129">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="3c262-130">101.02.55</span><span class="sxs-lookup"><span data-stu-id="3c262-130">101.02.55</span></span>

- <span data-ttu-id="3c262-131">Исправлена проблема, из-за которой продукт иногда не начинается после перезагрузки или обновления</span><span class="sxs-lookup"><span data-stu-id="3c262-131">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="3c262-132">Исправлена проблема, из-за которой параметры прокси не сохраняются при обновлении продукта</span><span class="sxs-lookup"><span data-stu-id="3c262-132">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="3c262-133">101.00.75</span><span class="sxs-lookup"><span data-stu-id="3c262-133">101.00.75</span></span>

- <span data-ttu-id="3c262-134">Добавлена поддержка следующих типов файловой системы: `ecryptfs` , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` и `vfat`</span><span class="sxs-lookup"><span data-stu-id="3c262-134">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="3c262-135">Новый синтаксис для [средства командной строки.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="3c262-135">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="3c262-136">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3c262-136">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="3c262-137">100.90.70</span><span class="sxs-lookup"><span data-stu-id="3c262-137">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="3c262-138">При обновлении установленного пакета из версии продукта до 100.90.70 обновление может привести к сбой в распространениях на основе red Hat и SLES.</span><span class="sxs-lookup"><span data-stu-id="3c262-138">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="3c262-139">Это из-за серьезного изменения пути файла.</span><span class="sxs-lookup"><span data-stu-id="3c262-139">This is because of a major change in a file path.</span></span> <span data-ttu-id="3c262-140">Временным решением является удаление старого пакета, а затем установка более нового пакета.</span><span class="sxs-lookup"><span data-stu-id="3c262-140">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="3c262-141">Эта проблема не существует в более новых версиях.</span><span class="sxs-lookup"><span data-stu-id="3c262-141">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="3c262-142">Исключения [антивирусов теперь поддерживают подкарды](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="3c262-142">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="3c262-143">Добавлена возможность [устранения проблем с производительностью](linux-support-perf.md) с помощью средства `mdatp` командной строки</span><span class="sxs-lookup"><span data-stu-id="3c262-143">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="3c262-144">Улучшения, чтобы сделать установку пакета более надежной</span><span class="sxs-lookup"><span data-stu-id="3c262-144">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="3c262-145">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3c262-145">Performance improvements & bug fixes</span></span>
