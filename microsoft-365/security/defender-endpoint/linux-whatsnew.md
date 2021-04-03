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
ms.openlocfilehash: 02a446f47ce4292b214c868e773802c53f7e3353
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581006"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a>Новые возможности в Microsoft Defender для конечной точки для Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- Улучшения производительности & исправлений ошибок

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- Улучшение производительности для ситуации, когда в список исключений антивируса добавляется вся точка установки. До этой версии файл, происходящий из точки установки, по-прежнему обрабатывался продуктом. Начиная с этой версии, действие файлов для исключенных точек установки подавляется, что приводит к более производительности продукта.
- Добавлен новый параметр в средство командной строки для просмотра сведений о последнем проверке по запросу. Чтобы просмотреть сведения о последнем проверке по запросу, запустите `mdatp health --details antivirus`
- Другие улучшения производительности & исправлений ошибок

## <a name="1011853"></a>101.18.53

- EDR для Linux теперь [общедоступна](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- Добавлен новый переключатель командной строки () для игнорирования исключений `--ignore-exclusions` av во время пользовательских сканирований ( `mdatp scan custom` )
- Расширенный `mdatp diagnostic create` с помощью нового параметра (), который позволяет сохранить журналы диагностики в другом `--path [directory]` каталоге
- Улучшения производительности & исправлений ошибок

## <a name="1011299"></a>101.12.99

- Улучшения производительности & исправлений ошибок

## <a name="1010476"></a>101.04.76

- Исправление ошибок

## <a name="1010348"></a>101.03.48

- Исправление ошибок

## <a name="1010255"></a>101.02.55

- Исправлена проблема, из-за которой продукт иногда не начинается после перезагрузки или обновления
- Исправлена проблема, из-за которой параметры прокси не сохраняются при обновлении продукта

## <a name="1010075"></a>101.00.75

- Добавлена поддержка следующих типов файловой системы: `ecryptfs` , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` и `vfat`
- Новый синтаксис для [средства командной строки.](linux-resources.md#configure-from-the-command-line)
- Улучшения производительности & исправлений ошибок

## <a name="1009070"></a>100.90.70

> [!WARNING]
> При обновлении установленного пакета из версии продукта до 100.90.70 обновление может привести к сбой в распространениях на основе red Hat и SLES. Это из-за серьезного изменения пути файла. Временным решением является удаление старого пакета, а затем установка более нового пакета. Эта проблема не существует в более новых версиях.

- Исключения [антивирусов теперь поддерживают подкарды](linux-exclusions.md#supported-exclusion-types)
- Добавлена возможность [устранения проблем с производительностью](linux-support-perf.md) с помощью средства `mdatp` командной строки
- Улучшения, чтобы сделать установку пакета более надежной
- Улучшения производительности & исправлений ошибок
