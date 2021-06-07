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
ms.openlocfilehash: 21a83c4876a90a231eb2a78d10a290be2dca2fa0
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782487"
---
# <a name="streaming-api"></a>Потоковый API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Поток событий advanced Hunting в концентраторы событий и/или учетную запись хранилища Azure.

Microsoft 365 Defender поддерживает потоковую трансляцию событий с помощью [advanced Hunting](../defender/advanced-hunting-overview.md) в [концентраторы](/azure/event-hubs/) событий и/или учетную запись [хранения Azure.](/azure/event-hubs/)



## <a name="in-this-section"></a>В этом разделе

Статья | Описание
:---|:---
[Поток событий в концентраторы событий Azure](streaming-api-event-hub.md)| Узнайте о том, как включите потоковый API в клиенте и настройте Microsoft 365 Defender для потоковой передачи [advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.
[Поток событий в учетную запись хранилища Azure](streaming-api-storage.md)| Узнайте о включите потоковый API в клиенте и настройте Microsoft 365 Defender для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в учетную запись хранилища Azure.


## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенных охоты](../defender/advanced-hunting-overview.md)
- [Документация по центрам событий Azure](/azure/event-hubs/)
- [служба хранилища Azure Документация по учетной записи](/azure/storage/common/storage-account-overview)
