---
title: Тип ресурса машины
description: Узнайте о методах и свойствах типа ресурсов Machine в Microsoft Defender для конечной точки.
keywords: apis, поддерживаемые apis, get, machines
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
ms.openlocfilehash: 5ca147c9e69168b2f15aa69bba8728567b782fa9
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984464"
---
# <a name="machine-resource-type"></a>Тип ресурса машины

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Методы

Метод|Возвращаемый тип |Описание
:---|:---|:---
[Список компьютеров](get-machines.md) | [коллекция](machine.md) машин | Список [сущностями](machine.md) машин в организации.
[Получить машину](get-machine-by-id.md) | [машина](machine.md) | Получите [машину по](machine.md) своему удостоверению.
[Вход в систему пользователей](get-machine-log-on-users.md) | Коллекция объектов [user](user.md) | Получите набор [пользователя,](user.md) который вошел в [компьютер.](machine.md)
[Получать связанные оповещения](get-machine-related-alerts.md) | Коллекция [alert](alerts.md) | Получите набор [сущностями](alerts.md) оповещений, которые были подняты на [компьютере.](machine.md)
[Получить установленное программное обеспечение](get-installed-software.md) | [коллекция программного](software.md) обеспечения | Извлекает коллекцию установленного программного обеспечения, связанного с данным iD машины.
[Получить обнаруженные уязвимости](get-discovered-vulnerabilities.md) | [коллекция уязвимостей](vulnerability.md) | Извлекает коллекцию обнаруженных уязвимостей, связанных с данным iD машины.
[Получить рекомендации по безопасности](get-security-recommendations.md) | [коллекция](recommendation.md) рекомендаций | Извлекает коллекцию рекомендаций по безопасности, связанных с данным ID машины.
[Добавление и удаление тегов компьютера](add-or-remove-machine-tags.md) | [машина](machine.md) | Добавление или удаление тега в определенную машину.
[Поиск компьютеров по протоколу IP](find-machines-by-ip.md) | [коллекция](machine.md) машин | Поиск машин с IP-адресом.
[Поиск компьютеров по тегу](find-machines-by-tag.md) | [коллекция](machine.md) машин | Поиск машин по [тегу](machine-tags.md).
[Получить недостающие КБ](get-missing-kbs-machine.md) | Коллекция KB | Получить список отсутствующих КБ, связанных с машинным ИД
[Установить значение устройства](set-device-value.md)| [коллекция](machine.md) машин | Установите [значение устройства.](tvm-assign-device-value.md)
[Машина обновления](update-machine-method.md) |[коллекция](machine.md) машин | Получите состояние обновления компьютера.

## <a name="properties"></a>Свойства

Свойство |   Тип   |   Описание
:---|:---|:---
id | String | [удостоверение](machine.md) компьютера.
computerDnsName | String | [полное](machine.md) имя машины.
firstSeen | DateTimeOffset | Первое свидание и [время,](machine.md) когда машина была замечена Microsoft Defender для конечной точки.
lastSeen | DateTimeOffset |Время и дата последнего полученного полного отчета о устройстве. Обычно устройство отправляет полный отчет каждые 24 часа.
osPlatform | String | Платформа операционной системы.
osProcessor | String | Процессор операционной системы. Вместо этого используйте свойство osArchitecture.
version | String | Версия операционной системы.
osBuild | Nullable long | Номер сборки операционной системы.
lastIpAddress | String | Последний IP-адрес локального NIC на [компьютере.](machine.md)
lastExternalIpAddress | String | Последний IP-адрес, [с помощью которого](machine.md) машина имеет доступ к Интернету.
healthStatus | Перечисление | [состояние состояния](machine.md) состояния компьютера. Возможные значения: "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" и "Unknown". 
rbacGroupName | String | Имя группы машин.
riskScore | Nullable Enum | Оценка риска, оцениваемая Microsoft Defender для конечной точки. Возможные значения: "Нет", "Информационный", "Низкий", "Средний" и "Высокий".
exposureScore | Nullable Enum | [Оценка экспозиции,](tvm-exposure-score.md) оцениваемая Microsoft Defender для конечной точки. Возможные значения: "Нет", "Низкий", "Средний" и "Высокий".
aadDeviceId | Nullable representation Guid | AAD Device ID (когда [машина](machine.md) является AAD Joined).
machineTags | Коллекция объектов string | Набор [тегов](machine.md) машин.
exposureLevel | Nullable Enum | Уровень экспозиции, оцениваемый Microsoft Defender для конечной точки. Возможные значения: "Нет", "Низкий", "Средний" и "Высокий".
deviceValue | Nullable Enum | Значение [устройства](tvm-assign-device-value.md). Возможные значения: "Нормальный", "Низкий" и "Высокий".
ipAddresses | Коллекция IpAddress | Набор ***объектов IpAddress.*** См. [API get machines](get-machines.md).
osArchitecture | String | Архитектура операционной системы. Возможные значения: "32-bit", "64-bit". Используйте это свойство вместо osProcessor.


