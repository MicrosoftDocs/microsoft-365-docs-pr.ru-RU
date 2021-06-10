---
title: Поддерживаемые API ответов Microsoft Defender для конечных точек
description: Узнайте о конкретных вызовах API API Microsoft Defender для конечной точки.
keywords: API ответа, api графа, поддерживаемые apis, actor, alerts, device, user, domain, ip, file
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933773"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>Поддерживаемые API запросов Для защитника Майкрософт для конечных точек 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

Сведения о поддерживаемых вызовах API, связанных с ответами, которые можно выполнить, а также сведения, такие как необходимые заглавные главы запросов и ожидаемый ответ от звонков.

## <a name="in-this-section"></a>В этом разделе
Статья | Описание
:---|:---
Сбор пакета исследования | Запустите этот API для сбора пакета исследований с устройства.
Изолировать устройство | Запустите этот API, чтобы изолировать устройство от сети.
Устройство Unisolate | Удалите устройство из изоляции. 
Ограничение выполнения кода | Запустите этот API, чтобы содержать атаку, остановив вредоносные процессы. Вы также можете заблокировать устройство и предотвратить последующие попытки запуска потенциально вредоносных программ.
Неограниченное выполнение кода | Запустите это, чтобы отменить ограничение политики приложений после проверки того, что скомпрометированное устройство исправлено.
Запуск проверки на вирусы | Удаленно инициировать антивирусное сканирование, чтобы помочь определить и устранять вредоносные программы, которые могут присутствовать на взломаемом устройстве.
Остановка и помещение на карантин файла |  Запустите этот вызов, чтобы остановить запуск процессов, карантиных файлов и удаление сохраняемости, например ключей реестра.
Пример запроса | Запустите этот вызов, чтобы запросить образец файла с определенного устройства. Файл будет собираться с устройства и загружаться в безопасное хранилище.
Файл блокировки | Запустите этот API, чтобы предотвратить дальнейшее распространение атаки в организации, запретив потенциально вредоносные файлы или подозрительные вредоносные программы. 
Разблокировка файла | Разрешить запуск файла в организации с помощью антивирусная программа в Microsoft Defender.
Получить пакет SAS URI | Запустите этот API, чтобы получить URI, который позволяет скачивать пакет исследования.
Получить объект MachineAction | Запустите этот API, чтобы получить объект MachineAction.
Получить коллекцию MachineActions | Запустите это, чтобы получить коллекцию MachineAction.
Получить коллекцию FileActions | Запустите этот API, чтобы получить коллекцию FileActions.
Получить объект FileMachineAction | Запустите этот API, чтобы получить объект FileMachineAction.
Получить коллекцию FileMachineActions | Запустите этот API, чтобы получить коллекцию FileMachineAction.
