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
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Новые возможности в Microsoft Defender для конечной точки в Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a>101.29.64 (30.121042.12964.0)

- Начиная с этой версии, угрозы, обнаруженные во время проверки антивирусов по запросу, срабатываемой через клиент командной строки, автоматически устраняются. Угрозы, обнаруженные во время сканирования, срабатываемого с помощью пользовательского интерфейса, по-прежнему требуют ручного действия.
- `mdatp diagnostic real-time-protection-statistics` теперь поддерживает два дополнительных коммутатора:
  - `--sort`: сортирует выход, убывающий по общему количеству отсканированных файлов
  - `--top N`: отображает верхние результаты N (работает только в том `--sort` случае, если указано)
- Улучшения производительности & исправлений ошибок

## <a name="1012572-30121022125630"></a>101.25.72 (30.121022.12563.0)

- Microsoft Defender для конечной точки на Linux теперь доступен в предварительном просмотре для государственных клиентов США. Дополнительные сведения см. в [веб-сайте Microsoft Defender for Endpoint для государственных клиентов США.](gov.md)
- Исправлена проблема, из-за которой использование Microsoft Defender для конечной точки в Linux в системах с файлами FUSE привело к зависаю ОС
- Улучшения производительности & других исправлений ошибок

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- Улучшения производительности & исправлений ошибок

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- Улучшение производительности для ситуации, когда в список исключений антивируса добавляется вся точка установки. До этой версии файл, происходящий из точки установки, по-прежнему обрабатывался продуктом. Начиная с этой версии, действие файлов для исключенных точек установки подавляется, что приводит к более производительности продукта.
- Добавлен новый параметр в средство командной строки для просмотра сведений о последнем проверке по запросу. Чтобы просмотреть сведения о последнем проверке по запросу, запустите `mdatp health --details antivirus`
- Другие улучшения производительности & исправлений ошибок

## <a name="1011853"></a>101.18.53

- EDR Для Linux теперь [обычно доступны](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
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
