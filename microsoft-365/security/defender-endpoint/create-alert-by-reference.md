---
title: Создание оповещений из API событий
description: Узнайте, как использовать API создания оповещений для создания нового оповещения в верхней части события в Microsoft Defender для конечной точки.
keywords: apis, api graph, supported apis, get, alert, information, id
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
ms.openlocfilehash: 8b05dde015bc96e1ccd3f80e25c416a371e03199
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772393"
---
# <a name="create-alert-api"></a>Создание API оповещений

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Описание API
Создает новое [оповещение](alerts.md) в верхней части **события**.
<br>**Для создания оповещений** требуется microsoft Defender for Endpoint Event.
<br>Вам потребуется предоставить 3 параметра события в запросе: **Время** события, **машинный ИД** и **ID отчета.** См. приведенный ниже пример.
<br>Вы можете использовать событие, найденное в API advanced Hunting или Portal.
<br>Если на том же устройстве существует открытое оповещение с тем же названием, новое созданное оповещение будет объединено с ним.
<br>Автоматическое расследование запускается автоматически при оповещениях, созданных с помощью API.


## <a name="limitations"></a>Ограничения
1. Ограничения скорости для этого API — 15 вызовов в минуту.


## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения |   Разрешение  |   Имя отображения разрешений
:---|:---|:---
Приложение |   Alerts.ReadWrite.All |  'Read and write all alerts'
Делегированные (рабочая или учебная учетная запись) | Alert.ReadWrite | 'Read and write alerts'

>[!Note]
> При получении маркера с помощью учетных данных пользователей:
>- У пользователя должно быть по крайней мере следующее разрешение на роль: "Оповещение о расследовании" (см. в рублях [Создание](user-roles.md) ролей и управление ими для получения дополнительных сведений)
>- Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).

## <a name="http-request"></a>HTTP-запрос

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Авторизация | String | Bearer {token}. **Обязательное поле**.
Content-Type | String | application/json. **Обязательное поле**.

## <a name="request-body"></a>Тело запроса

В теле запроса укажи следующие значения (все необходимые):

Свойство | Тип | Описание
:---|:---|:---
eventTime | DateTime (UTC) | Точное время события в качестве строки, полученной из продвинутой охоты. например. ```2018-08-03T16:45:21.7115183Z``` **Обязательно**.
reportId | String | ReportId события, полученный из продвинутой охоты. **Обязательное поле**.
machineId | String | Id устройства, на котором было идентифицировано событие. **Обязательное поле**.
severity | String | Степень серьезности оповещения. Значения свойств: "Low", "Medium" и "High". **Обязательное поле**.
title | String | Название для оповещений. **Обязательное поле**.
description | String | Описание оповещений. **Обязательное поле**.
recommendedAction| String | Действия, которые рекомендуется принимать сотрудником службы безопасности при анализе оповещения. **Обязательное поле**.
category| String | Категория оповещения. Значения свойств: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **required**.

## <a name="response"></a>Отклик

В случае успеха этот метод возвращает 200 [](alerts.md) ОК и новый объект оповещений в теле ответа. Если событие с указанными свойствами _(reportId,_ _eventTime_ и _machineId)_ не было найдено - 404 Не найдено.

## <a name="example"></a>Пример

**Запрос**

Ниже приведен пример запроса.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
