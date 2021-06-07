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
ms.openlocfilehash: 3e6d4df1c2c0f4934de1e8a54e8c1676aae230e3
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771631"
---
# <a name="raw-data-streaming-api"></a>Необработанные API потоковой передачи данных

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Поток событий advanced Hunting в концентраторы событий и/или учетную запись хранилища Azure.

Defender for Endpoint поддерживает потоковую трансляцию всех [](/azure/event-hubs/) событий, доступных с помощью [advanced Hunting,](advanced-hunting-overview.md) в концентраторы событий и/или учетную запись [хранилища Azure.](/azure/event-hubs/)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>В этом разделе

Статья | Описание
:---|:---
[Поток событий Microsoft Defender для конечных точек в концентраторы событий Azure](raw-data-export-event-hub.md)| Узнайте о том, как включите потоковый API в клиенте и настройте Defender для конечной точки для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в концентраторы событий.
[Stream Defender для событий конечной точки в учетной записи хранения Azure](raw-data-export-storage.md)| Узнайте о включите потоковый API в клиенте и настройте Defender для конечной точки для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в учетную запись хранилища Azure.


## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенных охоты](advanced-hunting-overview.md)
- [Документация по центрам событий Azure](/azure/event-hubs/)
- [служба хранилища Azure Документация по учетной записи](/azure/storage/common/storage-account-overview)