---
title: Stream Microsoft Defender for Endpoint event
description: Узнайте, как настроить ATP Microsoft Defender для потоковой передачи событий Advanced Hunting в центры событий или учетную запись хранилища Azure
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
ms.openlocfilehash: 22f4e4c974b60e291273eb9bebfa34583f4e2fb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071885"
---
# <a name="raw-data-streaming-api"></a>Необработанные API потоковой передачи данных

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Поток событий advanced Hunting в концентраторы событий и/или учетную запись хранилища Azure.

Defender for Endpoint поддерживает потоковую трансляцию всех [](https://docs.microsoft.com/azure/event-hubs/) событий, доступных с помощью [advanced Hunting,](advanced-hunting-overview.md) в концентраторы событий и/или учетную запись [хранилища Azure.](https://docs.microsoft.com/azure/event-hubs/)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>В этом разделе

Статья | Описание
:---|:---
[Поток событий Microsoft Defender для конечных точек в концентраторы событий Azure](raw-data-export-event-hub.md)| Узнайте о том, как включите потоковый API в клиенте и настройте Defender для конечной точки для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в концентраторы событий.
[Stream Defender для событий конечной точки в учетной записи хранения Azure](raw-data-export-storage.md)| Узнайте о включите потоковый API в клиенте и настройте Defender для конечной точки для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в учетную запись хранилища Azure.


## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенных охоты](advanced-hunting-overview.md)
- [Документация по центрам событий Azure](https://docs.microsoft.com/azure/event-hubs/)
- [Документация по учетной записи Хранилища Azure](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
