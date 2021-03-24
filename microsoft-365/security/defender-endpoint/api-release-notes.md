---
title: Заметки о выпуске API для Защитника Майкрософт для конечной точки
description: Заметки о выпуске обновлений, сделанных в набор API Для конечной точки Microsoft Defender для конечной точки.
keywords: защитник Майкрософт для записок выпуска api конечной точки, mde, apis, api mdatp, updates, notes, release
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
ms.technology: mde
ms.openlocfilehash: e37841fa17a5998c431c6a76b878f20ef1b06d10
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069845"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Заметки о выпуске API для Защитника Майкрософт для конечной точки

**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

В следующих сведениях перечислены обновления, сделанные в API Microsoft Defender для конечных точек, и даты, которые они были сделаны.


> [!TIP]
> RSS-канал. Получите уведомление об обновлении этой страницы путем копирования и вклейки следующего URL-адреса в читателя каналов: 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a>10.02.2021
<hr>

- Добавлен новый API: [пакетные оповещения об обновлении.](batch-update-alerts.md) 

<br>

### <a name="25012021"></a>25.01.2021
<hr>

- Обновленные ограничения скорости для [API предварительной](run-advanced-query-api.md) охоты от 15 до 45 запросов в минуту. 

<br>

### <a name="21012021"></a>21.01.2021
<hr>

- Добавлен новый API: [поиск устройств по тегу](machine-tags.md). 
- Добавлен новый API: [Показатели импорта.](import-ti-indicators.md) 

<br>

### <a name="03012021"></a>03.01.2021
<hr>

- Обновленные данные оповещения: добавлены ***detectionStatus** _, _*_parentProcessFilePath_*_ и _ *_parentProcessFileName_** свойства.
- Обновленный [объект Alert:](alerts.md) ***добавлено свойство detectorId.***

<br>

### <a name="15122020"></a>15.12.2020
<hr>

- Обновленная [сущность устройства:](machine.md) добавлен ***список IpInterfaces.*** См. [список устройств](get-machines.md).

<br>

### <a name="04112020"></a>04.11.2020
<hr>

- Добавлен новый API: [за установите значение устройства.](set-device-value.md)
- Обновленная [сущность устройства:](machine.md) ***добавлено свойство deviceValue.***

<br>

### <a name="01092020"></a>01.09.2020
<hr>

- Добавлена возможность расширения сущности Alert с помощью связанных с ней данных. См. [список оповещений](get-alerts.md).

<br>
<br>