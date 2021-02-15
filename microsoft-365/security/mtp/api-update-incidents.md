---
title: API обновления инцидентов
description: Узнайте, как обновлять инциденты с помощью API Защитника Microsoft 365
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929074"
---
# <a name="update-incidents-api"></a>API обновления инцидентов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>Описание API

Обновляет свойства существующего инцидента. Updatable properties are: ```status``` , , , , и ```determination``` ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Квоты, выделение ресурсов и другие ограничения

1. Вы можете делать до 50 вызовов в минуту или 1500 вызовов в час, прежде чем нажать порог регулирования.
2. Вы можете установить `determination` свойство, только если `classification` установлено свойство TruePositive.

Если ваш запрос регулирование, он возвращает `429` код ответа. В теле ответа будет указано время начала новых вызовов.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Чтобы узнать больше, включая выбор разрешений, [см. API Access в Microsoft 365 Defender.](api-access.md)

Тип разрешения | Разрешение | Отображаемая имя разрешения
-|-|-
Для приложений | Incident.ReadWrite.All | Чтение и написание всех инцидентов
Делегированные (рабочая или учебная учетная запись) | Incident.ReadWrite | Чтение и написание инцидентов

> [!NOTE]
> При получении маркера с использованием учетных данных пользователя у пользователя должно быть разрешение на обновление инцидента на портале.

## <a name="http-request"></a>HTTP-запрос

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
-|-|-
Authorization | String | Bearer {token}. **Обязательное поле**.
Content-Type | String | application/json. **Обязательное поле**.

## <a name="request-body"></a>Основной текст запроса

В теле запроса укавите значения для полей, которые необходимо обновить. Существующие свойства, не включенные в тело запроса, сохраняют свои значения, если их не придется пересчитывать из-за изменений связанных значений. Для лучшей производительности следует опустить существующие значения, которые не изменились.

Свойство | Тип | Описание
-|-|-
status | Перечисление | Указывает текущее состояние оповещения. Возможные значения: ```Active``` , ```Resolved``` и ```Redirected``` .
assignedTo | string | Владелец инцидента.
classification | Перечисление | Спецификация оповещения. Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.
определение | Перечисление | Определяет определение оповещения. Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | string List | Список тегов инцидента.

## <a name="response"></a>Отклик

В случае успеха этот метод возвращает `200 OK` . Тело ответа будет содержать сущность инцидента с обновленными свойствами. Если инцидент с указанным ИД не найден, метод `404 Not Found` возвращается.

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

## <a name="related-articles"></a>Статьи по теме

- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Узнайте об ограничениях API и лицензировании](api-terms.md)
- [Коды ошибок](api-error-codes.md)
- [Программные интерфейсы, относящиеся к инцидентам](api-incident.md)
- [Получение списка инцидентов](api-list-incidents.md)
- [Обзор инцидентов](incidents-overview.md)
