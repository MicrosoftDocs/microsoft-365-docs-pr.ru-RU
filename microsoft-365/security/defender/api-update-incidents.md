---
title: Обновление API инцидента
description: Узнайте, как обновлять инциденты с Microsoft 365 Defender API
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
ms.openlocfilehash: 60f1209331862eb21d3b1949265f0873dcf2e5a7
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287823"
---
# <a name="update-incidents-api"></a>Обновление API инцидентов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

## <a name="api-description"></a>Описание API

Обновляет свойства существующего инцидента. Updatable свойства: ```status``` ```determination``` , , , ```classification``` и ```assignedTo``` ```tags``` ```comments``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Квоты, распределение ресурсов и другие ограничения

1. Вы можете сделать до 50 вызовов в минуту или 1500 вызовов в час, прежде чем нажать порог регулирования.
2. Свойство можно установить `determination` только в том `classification` случае, если установлено truePositive.

Если ваш запрос будет отламыт, он вернет `429` код ответа. В теле ответа будет указано время, когда можно приступить к новым вызовам.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные возможности, в том числе выбор разрешений, см. в Microsoft 365 Defender [API.](api-access.md)

Тип разрешения | Разрешение | Имя отображения разрешений
-|-|-
Application | Incident.ReadWrite.All | Чтение и написание всех инцидентов
Делегированные (рабочая или учебная учетная запись) | Incident.ReadWrite | Чтение и написание инцидентов

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
status | Перечисление | Указывает текущее состояние инцидента. Возможные значения: ```Active``` , ```Resolved``` и ```Redirected``` .
assignedTo | Строка | Владелец инцидента.
classification | Перечисление | Спецификация инцидента. Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.
определение | Перечисление | Указывает определение инцидента. Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | строка Список | Список тегов Инцидент.
comment | string | Комментарий, который следует добавить к инциденту.

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
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>Связанные статьи

- [Доступ к Microsoft 365 Defender API](api-access.md)
- [Узнайте о ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)
- [Программные интерфейсы, относящиеся к инцидентам](api-incident.md)
- [Получение списка инцидентов](api-list-incidents.md)
- [Обзор инцидентов](incidents-overview.md)
