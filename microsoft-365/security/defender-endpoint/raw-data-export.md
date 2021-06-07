---
title: Stream Microsoft Defender for Endpoint event
description: Узнайте, как настроить Microsoft Defender для конечной точки для потоковой передачи событий advanced Hunting в концентраторы событий или учетную запись хранилища Azure
keywords: экспорт необработанных данных, потоковый API, API, концентраторы событий, хранилище Azure, учетная запись хранилища, расширенный доступ к данным, обмен необработанные данные
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: c8403dee11070dcf0825fad2502d8d21d54933fd
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782757"
---
# <a name="raw-data-streaming-api"></a>Необработанные API потоковой передачи данных

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Поток событий advanced Hunting в концентраторы событий и/или учетную запись хранилища Azure.


Microsoft Defender для конечной точки поддерживает потоковые [](/azure/event-hubs/) события, доступные с помощью [advanced Hunting](../defender/advanced-hunting-overview.md) для учетных записей хранения событий и/или [Azure.](/azure/storage/common/storage-account-overview)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>В этом разделе

Статья | Описание
:---|:---
[Поток событий Microsoft Defender для конечных точек в концентраторы событий Azure](raw-data-export-event-hub.md)| Узнайте о том, как включите потоковый API в клиенте и настройте Defender для конечной точки для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в концентраторы событий.
[Stream Defender для событий конечной точки в учетной записи хранения Azure](raw-data-export-storage.md)| Узнайте о включите потоковый API в клиенте и настройте Defender для конечной точки для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в учетную запись хранилища Azure.


## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенных охоты](advanced-hunting-overview.md)
- [Документация по центрам событий Azure](/azure/event-hubs/)
- [служба хранилища Azure Документация по учетной записи](/azure/storage/common/storage-account-overview)