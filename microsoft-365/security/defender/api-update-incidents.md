---
title: Обновление API инцидента
description: Узнайте, как обновлять инциденты с помощью Microsoft 365 Defender API
keywords: обновление, api, инцидент
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
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571785"
---
# <a name="update-incident-api"></a>Обновление API инцидента

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

## <a name="api-description"></a>Описание API

Обновляет свойства существующего инцидента. Updatable свойства: ```status``` , ```determination``` , , , ```classification``` и ```assignedTo``` ```tags``` ```comments``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Квоты, распределение ресурсов и другие ограничения

1. Вы можете сделать до 50 звонков в минуту или 1500 звонков в час, прежде чем вы нажмете порог регулирования.
2. Вы можете установить свойство только `determination` в том случае, `classification` если настроено на TruePositive.

Если ваш запрос будет задушен, он вернет `429` код ответа. Орган ответа укажет время, когда вы можете начать делать новые звонки.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Чтобы узнать больше, в том числе о том, как выбрать разрешения, [Microsoft 365 API Defender.](api-access.md)

Тип разрешения | Разрешение | Имя дисплея разрешения
-|-|-
Приложение | Инцидент.ReadWrite.All | Читать и писать все инциденты
Делегированное (рабочая или учебная учетная запись) | Инцидент.ReadWrite | Инциденты чтения и записи

> [!NOTE]
> При получении токена с помощью учетных данных пользователя необходимо иметь разрешение на обновление инцидента на портале.

## <a name="http-request"></a>HTTP-запрос

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
-|-|-
Authorization | String | Носитель (токен). **Обязательное поле**.
Content-Type | String | application/json. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса

В органе запроса утетете значения полей, которые должны быть обновлены. Существующие свойства, не включенные в тело запроса, сохранят свои значения, если только они не должны быть пересчитаны из-за изменений связанных значений. Для лучшей производительности следует опустить существующие значения, которые не изменились.

Свойство | Тип | Описание
-|-|-
status | Перечисление | Уточняется текущее состояние происшествия. Возможные значения: ```Active``` ```Resolved``` , и ```Redirected``` .
assignedTo | Строка | Владелец инцидента.
classification | Перечисление | Спецификация инцидента. Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.
решимость | Перечисление | Уточняется определение инцидента. Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | строка Список | Список тегов инцидента.
comment | string | Комментарий, который будет добавлен к инциденту.

## <a name="response"></a>Отклик

В случае успеха этот метод `200 OK` возвращается. Орган реагирования будет содержать сущность инцидента с обновленными свойствами. Если инцидент с указанным идентификатором не найден, метод `404 Not Found` возвращается.

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

- [Доступ к Microsoft 365-имуме защитника](api-access.md)
- [Узнайте об ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)
- [Программные интерфейсы, относящиеся к инцидентам](api-incident.md)
- [Получение списка инцидентов](api-list-incidents.md)
- [Обзор инцидентов](incidents-overview.md)
