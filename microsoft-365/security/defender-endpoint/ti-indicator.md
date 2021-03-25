---
title: Тип ресурса индикатора
description: Укажите сведения об объекте и определите срок действия индикатора с помощью Microsoft Defender для конечной точки.
keywords: apis, поддерживаемые apis, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187312"
---
# <a name="indicator-resource-type"></a>Тип ресурса индикатора

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- См. [соответствующую страницу Индикаторы](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) на портале. 

Метод|Возвращаемый тип |Описание
:---|:---|:---
[Индикаторы списка](get-ti-indicators-collection.md) | [Индикатор](ti-indicator.md) Коллекция | [Сущностями индикатора](ti-indicator.md) списка.
[Отправка индикатора](post-ti-indicator.md) | [Индикатор](ti-indicator.md) | Отправка или обновление [объекта индикатора.](ti-indicator.md)
[Индикаторы импорта](import-ti-indicators.md) | [Индикатор](ti-indicator.md) Коллекция | Отправка или [обновление сущностями](ti-indicator.md) Индикаторы.
[Удаление индикатора](delete-ti-indicator-by-id.md) | Содержимое отсутствует | Удаляет объект [Indicator.](ti-indicator.md)


## <a name="properties"></a>Свойства
Свойство |  Тип    |   Описание
:---|:---|:---
id | Строка | Удостоверение сущности [индикатора.](ti-indicator.md)
indicatorValue | Строка | Значение [индикатора](ti-indicator.md).
indicatorType | Перечисление | Тип индикатора. Возможные значения: "FileSha1", "FileSha256", "IpAddress", "DomainName" и "URL".
приложение | Строка | Приложение, связанное с индикатором. 
action | Перечисление | Действие, которое будет принято, если индикатор будет обнаружен в организации. Возможные значения: "Alert", "AlertAndBlock" и "Allowed".
sourceType | Перечисление | "Пользователь" в случае, если индикатор, созданный пользователем (например, с портала), "AadApp" в случае его отправки с помощью автоматического приложения через API.
source | строка | Имя пользователя или приложения, которое представило индикатор.
createdBy | String | Уникальный идентификатор пользователя или приложения, подающего индикатор.
lastUpdatedBy | Строка | Удостоверение пользователя или приложения, который последний раз обновлял индикатор.
creationTimeDateTimeUtc | DateTimeOffset | Дата и время создания индикатора.
expirationTime | DateTimeOffset | Срок действия индикатора.
lastUpdateTime | DateTimeOffset | Последний раз индикатор обновлялся.
severity | Перечисление | Серьезность индикатора. Возможные значения: "Информационная", "Низкая", "Средняя" и "Высокая".
title | Строка | Название индикатора.
description | Строка | Описание индикатора.
recommendedActions | Строка | Рекомендуемые действия для индикатора.
rbacGroupNames | Список строк | Имена групп устройств RBAC, в которых индикатор выставлен и активен. Пустой список в случае, если он будет выставлен на все устройства.


## <a name="json-representation"></a>Представление Json

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
