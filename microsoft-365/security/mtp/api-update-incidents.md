---
title: API обновления инцидентов
description: Узнайте, как обновлять инциденты с помощью API защиты от угроз Майкрософт
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
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650478"
---
# <a name="update-incidents-api"></a>API обновления инцидентов

**Область применения:**
- Защита от угроз (Майкрософт)

>[!IMPORTANT] 
>Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>Описание API
Обновляет свойства существующего инцидента.
<br>Обновляемые свойства: ```status``` , ```determination``` , ```classification``` ```assignedTo``` и ```tags``` .


## <a name="limitations"></a>Ограничения
1. Ограничения частоты для этого API: 50 вызовов в минуту и 1500 вызовов в час.
2. Можно задать значение только в том ```determination``` случае, если для классификации задано значение труепоситиве.


## <a name="permissions"></a>Разрешения
Для вызова этого API требуется одно из следующих разрешений. Чтобы узнать больше, в том числе как выбирать разрешения, ознакомьтесь со статьей [доступ к API Microsoft Threat protection](api-access.md).

Тип разрешения |   Разрешение  |   Отображаемое имя разрешения
:---|:---|:---
Для приложений |   Инцидент. ReadWrite. ALL |    "Чтение и запись всех инцидентов"
Делегированные (рабочая или учебная учетная запись) | Инцидент. ReadWrite | "Чтение и запись происшествий"

>[!NOTE]
> При получении маркера с использованием учетных данных пользователя:
>- Пользователь должен иметь разрешение на обновление инцидента на портале.


## <a name="http-request"></a>HTTP-запрос

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | String | Bearer {Token}. **Обязательное поле**.
Content-Type | String | application/json. **Обязательное поле**.


## <a name="request-body"></a>Тело запроса
В тексте запроса укажите значения для соответствующих полей, которые необходимо обновить.
<br>Предыдущие значения существующих свойств, не включенных в текст запроса, останутся прежними или будут повторно вычислены с учетом измененных значений других свойств. 
<br>Для лучшей производительности не следует включать существующие значения, которые не были изменены.

Свойство | Тип | Описание
:---|:---|:---
status | Перечисление | Указывает текущее состояние оповещения. Возможные значения: ```Active``` ```Resolved``` и ```Redirected``` .
assignedTo | string | Владелец инцидента.
classification | Перечисление | Спецификация оповещения. Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.
решение | Перечисление | Задает определение оповещения. Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Список строк | Список тегов инцидента.



## <a name="response"></a>Отклик
В случае успешного выполнения этот метод возвращает 200 ОК, а сущность инцидента в тексте отклика с обновленными свойствами. Если инцидент с указанным идентификатором не найден — 404 не найдено.


## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>Связанная тема
- [API инцидентов](api-incident.md)
- [Список инцидентов](api-list-incidents.md)