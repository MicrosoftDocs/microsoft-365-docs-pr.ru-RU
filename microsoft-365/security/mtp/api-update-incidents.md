---
title: API обновления инцидентов
description: Узнайте, как обновлять инциденты с помощью API Защитника Microsoft 365
keywords: обновление, API, инцидент
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719408"
---
# <a name="update-incidents-api"></a>API обновления инцидентов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>Описание API

Обновляет свойства существующего инцидента. Updatable properties are: ```status``` , , , and ```determination``` ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Квоты, выделение ресурсов и другие ограничения

1. Вы можете сделать до 50 вызовов в минуту или 1500 вызовов в час, прежде чем нажать порог регулирования.
2. Вы можете установить `determination` свойство, только если `classification` установлено свойство TruePositive.

Если ваш запрос регулирование, он возвращает `429` код ответа. В теле ответа будет указано время начала новых вызовов.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Чтобы узнать больше, включая выбор разрешений, [см. API Access в Microsoft 365 Defender.](api-access.md)

Тип разрешения | Разрешение | Отображаемая имя разрешения
-|-|-
Приложение | Incident.ReadWrite.All | Чтение и написание всех инцидентов
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
Авторизация | String | Bearer {token}. **Обязательное поле**.
Content-Type | String | application/json. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса

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
