---
title: Заметки о выпуске API для Защитника Майкрософт для конечной точки
description: Заметки о выпуске обновлений, сделанных в набор API Для конечной точки Microsoft Defender для конечной точки.
keywords: Заметки о выпуске API для Защитника Майкрософт для конечных точек, mde, API API, Microsoft Defender для endpoint, обновления, заметки, выпуск
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a0191a52c64b32b314d4b2f2f36c85b060226ad6
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984656"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Заметки о выпуске API для Защитника Майкрософт для конечной точки

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

В следующих сведениях перечислены обновления, сделанные в API Microsoft Defender для конечных точек, и даты, которые они были сделаны.

> [!TIP]
> RSS-канал. Получите уведомление об обновлении этой страницы путем копирования и вклейки следующего URL-адреса в читателя каналов:
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>Заметки о выпуске — самые новые для самых старых (dd.mm.yyyyy)

### <a name="06102021"></a>06.10.2021

- Добавлен новый метод API оценки экспорта — метод оценки уязвимостей программного обеспечения _Delta Export (OData)_ Методы оценки экспорта и [свойства каждого устройства.](get-assessment-methods-properties.md)

### <a name="05252021"></a>05.25.2021

- Добавлены новые методы и свойства оценки экспорта API [на устройство.](get-assessment-methods-properties.md)

### <a name="03052021"></a>03.05.2021

- Добавлен новый API: [методы](get-remediation-methods-properties.md)и свойства действий по исправлению.

### <a name="10022021"></a>10.02.2021

- Добавлен новый API: [пакетные оповещения об обновлении.](batch-update-alerts.md)

### <a name="25012021"></a>25.01.2021

- Обновленные ограничения скорости для [API предварительной](run-advanced-query-api.md) охоты от 15 до 45 запросов в минуту.

### <a name="21012021"></a>21.01.2021

- Добавлен новый API: [поиск устройств по тегу](machine-tags.md).
- Добавлен новый API: [Показатели импорта.](import-ti-indicators.md)

### <a name="03012021"></a>03.01.2021

- Обновленные данные оповещения: добавлены ***detectionStatus** _, _*_parentProcessFilePath_*_ и _ *_parentProcessFileName_** свойства.
- Обновленный [объект Alert:](alerts.md) ***добавлено свойство detectorId.***

### <a name="15122020"></a>15.12.2020

- Обновленная [сущность устройства:](machine.md) добавлен ***список IpInterfaces.*** См. [список устройств](get-machines.md).

### <a name="04112020"></a>04.11.2020

- Добавлен новый API: [за установите значение устройства.](set-device-value.md)
- Обновленная [сущность устройства:](machine.md) ***добавлено свойство deviceValue.***

### <a name="01092020"></a>01.09.2020

- Добавлена возможность расширения сущности Alert с помощью связанных с ней данных. См. [список оповещений](get-alerts.md).
