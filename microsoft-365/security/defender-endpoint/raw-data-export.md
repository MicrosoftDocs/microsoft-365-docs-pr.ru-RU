---
title: События Microsoft 365 Defender
description: Узнайте, как настроить Microsoft 365 Defender для потоковой передачи событий advanced Hunting в центры событий или учетную запись хранения Azure
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
ms.openlocfilehash: 971cc757dcbd0a190917d2a5f11eb7f68b758008
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778201"
---
# <a name="streaming-api"></a>Потоковый API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Поток событий advanced Hunting в концентраторы событий и/или учетную запись хранилища Azure.

Microsoft 365 Defender поддерживает потоковую передачу всех событий, доступных с помощью [Advanced Hunting,](../defender/advanced-hunting-overview.md) в учетную запись хранилища [Event Hubs](/azure/event-hubs/) и/или [Azure.](/azure/event-hubs/)



## <a name="in-this-section"></a>В этом разделе

Статья | Описание
:---|:---
[Поток событий в концентраторы событий Azure](raw-data-export-event-hub.md)| Узнайте о том, как включите потоковый API в клиенте и настройте Microsoft 365 Defender для потоковой передачи [advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.
[Поток событий в учетную запись хранилища Azure](raw-data-export-storage.md)| Узнайте о включите потоковый API в клиенте и настройте Microsoft 365 Defender для потоковой передачи [advanced Hunting](../defender/advanced-hunting-overview.md) в учетную запись хранилища Azure.


## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенных охоты](../defender/advanced-hunting-overview.md)
- [Документация по центрам событий Azure](/azure/event-hubs/)
- [служба хранилища Azure Документация по учетной записи](/azure/storage/common/storage-account-overview)
