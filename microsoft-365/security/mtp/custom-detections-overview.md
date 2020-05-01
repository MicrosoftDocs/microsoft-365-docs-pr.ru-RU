---
title: Обзор пользовательских обнаружений в защите от угроз Майкрософт
description: Сведения об использовании расширенного поиска для создания пользовательских обнаружений и создания оповещений
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, пользовательские обнаружения, схема, Кусто, Microsoft 365, защита от угроз Майкрософт
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a9ba61650b69e3c42506735c90ae05b917a53209
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42931748"
---
# <a name="custom-detections-overview"></a>Обзор настраиваемых обнаружений

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

С помощью пользовательских обнаружений можно отслеживать различные события и состояния системы и отвечать на них, в том числе подозреваемые и неправильно настроенные конечные точки. Это можно сделать с помощью настраиваемых правил обнаружения, которые автоматически запускают оповещения и действия ответа.

Пользовательские проверки работают с [расширенным](advanced-hunting-overview.md)поиском, который предоставляет мощный, гибкий язык запросов, охватывающий широкий набор событий и системных сведений в сети. Вы можете настроить их для запуска через определенные интервалы, создавая оповещения и отменяя действия ответа при обнаружении совпадений.

Пользовательские обнаружения предоставляют:
- Оповещения об определениях, основанных на правилах, основанных на расширенных запросах поиска
- Действия при автоматическом отклике

## <a name="related-topic"></a>Связанная тема
- [Создание настраиваемых правил обнаружения и управление ими](custom-detection-rules.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)