---
title: Обновление API инцидентов
description: Узнайте, как обновлять инциденты с помощью API защитника Microsoft 365
keywords: обновление, API, инцидент
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 549f9bf2b9dc2ea5d1c734a809ad10a168c8123e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068973"
---
# <a name="update-incidents-api"></a>Обновление API инцидентов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

## <a name="api-description"></a>Описание API

Обновляет свойства существующего инцидента. Updatable свойства: ```status``` , ```determination``` , , , ```classification``` и ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Квоты, распределение ресурсов и другие ограничения

1. Вы можете сделать до 50 вызовов в минуту или 1500 вызовов в час, прежде чем нажать порог регулирования.
2. Свойство можно установить `determination` только в том `classification` случае, если установлено truePositive.

Если ваш запрос будет отламыт, он вернет `429` код ответа. В теле ответа будет указано время, когда можно приступить к новым вызовам.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные возможности, в том числе выбор разрешений, см. в записи [Access the Microsoft 365 Defender API.](api-access.md)

Тип разрешения | Разрешение | Имя отображения разрешений
-|-|-
Приложение | Incident.ReadWrite.All | Чтение и написание всех инцидентов
Делегированное (рабочая или учебная учетная запись) | Incident.ReadWrite | Чтение и написание инцидентов

> [!NOTE]
> При получении маркера с помощью учетных данных пользователей пользователю необходимо иметь разрешение на обновление инцидента на портале.

## <a name="http-request"></a>HTTP-запрос

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
-|-|-
Authorization | Строка | Bearer {token}. **Обязательное поле**.
Content-Type | String | application/json. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса

В теле запроса укажи значения для полей, которые должны быть обновлены. Существующие свойства, не включенные в тело запроса, будут поддерживать свои значения, если их не пересчитать из-за изменений связанных значений. Для лучшей производительности следует не использовать существующие значения, которые не изменились.

Свойство | Тип | Описание
-|-|-
status | Перечисление | Указывает текущее состояние оповещений. Возможные значения: ```Active``` , ```Resolved``` и ```Redirected``` .
assignedTo | строка | Владелец инцидента.
classification | Перечисление | Спецификация оповещений. Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.
определение | Перечисление | Указывает определение оповещений. Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | строка Список | Список тегов Инцидент.

## <a name="response"></a>Отклик

В случае успешной работы этот метод `200 OK` возвращается. Тело ответа будет содержать объект инцидента с обновленными свойствами. Если инцидент с указанным ID не найден, метод `404 Not Found` возвращается.

## <a name="example"></a>Пример

**Запрос**

Вот пример запроса.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Отклик**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a>Связанные статьи

- [Доступ к API защитника Microsoft 365](api-access.md)
- [Узнайте о ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)
- [Программные интерфейсы, относящиеся к инцидентам](api-incident.md)
- [Получение списка инцидентов](api-list-incidents.md)
- [Обзор инцидентов](incidents-overview.md)
