---
title: Новые возможности в Microsoft Defender для конечной точки для Linux
description: Список основных изменений для ATP Защитника Microsoft для Linux.
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
ms.openlocfilehash: dc3d775aced2ea3da42312cbf5a4d5e5af9fae50
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198781"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="3039e-104">Новые возможности в Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="3039e-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012364-30121021123640"></a><span data-ttu-id="3039e-105">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="3039e-105">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="3039e-106">Улучшение производительности для ситуации, когда в список исключений антивируса добавляется вся точка установки.</span><span class="sxs-lookup"><span data-stu-id="3039e-106">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="3039e-107">До этой версии файл, происходящий из точки установки, по-прежнему обрабатывался продуктом.</span><span class="sxs-lookup"><span data-stu-id="3039e-107">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="3039e-108">Начиная с этой версии, действие файлов для исключенных точек установки подавляется, что приводит к более производительности продукта.</span><span class="sxs-lookup"><span data-stu-id="3039e-108">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="3039e-109">Добавлен новый параметр в средство командной строки для просмотра сведений о последнем проверке по запросу.</span><span class="sxs-lookup"><span data-stu-id="3039e-109">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="3039e-110">Чтобы просмотреть сведения о последнем проверке по запросу, запустите `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="3039e-110">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="3039e-111">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3039e-111">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="3039e-112">101.18.53</span><span class="sxs-lookup"><span data-stu-id="3039e-112">101.18.53</span></span>

- <span data-ttu-id="3039e-113">EDR для Linux теперь [общедоступна](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="3039e-113">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="3039e-114">Добавлен новый переключатель командной строки () для игнорирования исключений `--ignore-exclusions` av во время пользовательских сканирований ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="3039e-114">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="3039e-115">Расширенный `mdatp diagnostic create` с помощью нового параметра (), который позволяет сохранить журналы диагностики в другом `--path [directory]` каталоге</span><span class="sxs-lookup"><span data-stu-id="3039e-115">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="3039e-116">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3039e-116">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="3039e-117">101.12.99</span><span class="sxs-lookup"><span data-stu-id="3039e-117">101.12.99</span></span>

- <span data-ttu-id="3039e-118">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3039e-118">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="3039e-119">101.04.76</span><span class="sxs-lookup"><span data-stu-id="3039e-119">101.04.76</span></span>

- <span data-ttu-id="3039e-120">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="3039e-120">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="3039e-121">101.03.48</span><span class="sxs-lookup"><span data-stu-id="3039e-121">101.03.48</span></span>

- <span data-ttu-id="3039e-122">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="3039e-122">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="3039e-123">101.02.55</span><span class="sxs-lookup"><span data-stu-id="3039e-123">101.02.55</span></span>

- <span data-ttu-id="3039e-124">Исправлена проблема, из-за которой продукт иногда не начинается после перезагрузки или обновления</span><span class="sxs-lookup"><span data-stu-id="3039e-124">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="3039e-125">Исправлена проблема, из-за которой параметры прокси не сохраняются при обновлении продукта</span><span class="sxs-lookup"><span data-stu-id="3039e-125">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="3039e-126">101.00.75</span><span class="sxs-lookup"><span data-stu-id="3039e-126">101.00.75</span></span>

- <span data-ttu-id="3039e-127">Добавлена поддержка следующих типов файловой системы: `ecryptfs` , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` и `vfat`</span><span class="sxs-lookup"><span data-stu-id="3039e-127">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="3039e-128">Новый синтаксис для [средства командной строки.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="3039e-128">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="3039e-129">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3039e-129">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="3039e-130">100.90.70</span><span class="sxs-lookup"><span data-stu-id="3039e-130">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="3039e-131">При обновлении установленного пакета из версии продукта до 100.90.70 обновление может привести к сбой в распространениях на основе red Hat и SLES.</span><span class="sxs-lookup"><span data-stu-id="3039e-131">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="3039e-132">Это из-за серьезного изменения пути файла.</span><span class="sxs-lookup"><span data-stu-id="3039e-132">This is because of a major change in a file path.</span></span> <span data-ttu-id="3039e-133">Временным решением является удаление старого пакета, а затем установка более нового пакета.</span><span class="sxs-lookup"><span data-stu-id="3039e-133">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="3039e-134">Эта проблема не существует в более новых версиях.</span><span class="sxs-lookup"><span data-stu-id="3039e-134">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="3039e-135">Исключения [антивирусов теперь поддерживают подкарды](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="3039e-135">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="3039e-136">Добавлена возможность [устранения проблем с производительностью](linux-support-perf.md) с помощью средства `mdatp` командной строки</span><span class="sxs-lookup"><span data-stu-id="3039e-136">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="3039e-137">Улучшения, чтобы сделать установку пакета более надежной</span><span class="sxs-lookup"><span data-stu-id="3039e-137">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="3039e-138">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="3039e-138">Performance improvements & bug fixes</span></span>
