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
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070486"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="92bd1-104">Новые возможности в Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="92bd1-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a><span data-ttu-id="92bd1-105">101.18.53</span><span class="sxs-lookup"><span data-stu-id="92bd1-105">101.18.53</span></span>

- <span data-ttu-id="92bd1-106">EDR для Linux теперь [общедоступна](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="92bd1-106">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="92bd1-107">Добавлен новый переключатель командной строки () для игнорирования исключений `--ignore-exclusions` av во время пользовательских сканирований ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="92bd1-107">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="92bd1-108">Расширенный `mdatp diagnostic create` с помощью нового параметра (), который позволяет сохранить журналы диагностики в другом `--path [directory]` каталоге</span><span class="sxs-lookup"><span data-stu-id="92bd1-108">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="92bd1-109">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="92bd1-109">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="92bd1-110">101.12.99</span><span class="sxs-lookup"><span data-stu-id="92bd1-110">101.12.99</span></span>

- <span data-ttu-id="92bd1-111">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="92bd1-111">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="92bd1-112">101.04.76</span><span class="sxs-lookup"><span data-stu-id="92bd1-112">101.04.76</span></span>

- <span data-ttu-id="92bd1-113">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="92bd1-113">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="92bd1-114">101.03.48</span><span class="sxs-lookup"><span data-stu-id="92bd1-114">101.03.48</span></span>

- <span data-ttu-id="92bd1-115">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="92bd1-115">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="92bd1-116">101.02.55</span><span class="sxs-lookup"><span data-stu-id="92bd1-116">101.02.55</span></span>

- <span data-ttu-id="92bd1-117">Исправлена проблема, из-за которой продукт иногда не начинается после перезагрузки или обновления</span><span class="sxs-lookup"><span data-stu-id="92bd1-117">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="92bd1-118">Исправлена проблема, из-за которой параметры прокси не сохраняются при обновлении продукта</span><span class="sxs-lookup"><span data-stu-id="92bd1-118">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="92bd1-119">101.00.75</span><span class="sxs-lookup"><span data-stu-id="92bd1-119">101.00.75</span></span>

- <span data-ttu-id="92bd1-120">Добавлена поддержка следующих типов файловой системы: `ecryptfs` , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` и `vfat`</span><span class="sxs-lookup"><span data-stu-id="92bd1-120">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="92bd1-121">Новый синтаксис для [средства командной строки.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="92bd1-121">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="92bd1-122">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="92bd1-122">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="92bd1-123">100.90.70</span><span class="sxs-lookup"><span data-stu-id="92bd1-123">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="92bd1-124">При обновлении установленного пакета из версии продукта до 100.90.70 обновление может привести к сбой в распространениях на основе red Hat и SLES.</span><span class="sxs-lookup"><span data-stu-id="92bd1-124">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="92bd1-125">Это из-за серьезного изменения пути файла.</span><span class="sxs-lookup"><span data-stu-id="92bd1-125">This is because of a major change in a file path.</span></span> <span data-ttu-id="92bd1-126">Временным решением является удаление старого пакета, а затем установка более нового пакета.</span><span class="sxs-lookup"><span data-stu-id="92bd1-126">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="92bd1-127">Эта проблема не существует в более новых версиях.</span><span class="sxs-lookup"><span data-stu-id="92bd1-127">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="92bd1-128">Исключения [антивирусов теперь поддерживают подкарды](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="92bd1-128">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="92bd1-129">Добавлена возможность [устранения проблем с производительностью](linux-support-perf.md) с помощью средства `mdatp` командной строки</span><span class="sxs-lookup"><span data-stu-id="92bd1-129">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="92bd1-130">Улучшения, чтобы сделать установку пакета более надежной</span><span class="sxs-lookup"><span data-stu-id="92bd1-130">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="92bd1-131">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="92bd1-131">Performance improvements & bug fixes</span></span>
