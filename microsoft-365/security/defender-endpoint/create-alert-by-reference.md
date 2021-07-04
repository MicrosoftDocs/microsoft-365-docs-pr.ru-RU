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
ms.openlocfilehash: 7f8d3b10cee0b3c4a561dfd1f7567fa9818e7686
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289467"
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

- **Для создания оповещений** требуется microsoft Defender for Endpoint Event.
- Вам потребуется предоставить 3 параметра события в запросе: **Время** события, **машинный ИД** и **ID отчета.** См. приведенный ниже пример.
- Вы можете использовать событие, найденное в API advanced Hunting или Portal.
- Если на том же устройстве существует открытое оповещение с тем же названием, новое созданное оповещение будет объединено с ним.
- Автоматическое расследование запускается автоматически при оповещениях, созданных с помощью API.

## <a name="limitations"></a>Ограничения

1. Ограничения скорости для этого API — 15 вызовов в минуту.

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
:---|:---|:---
Application | Alerts.ReadWrite.All | 'Read and write all alerts'
Делегированные (рабочая или учебная учетная запись) | Alert.ReadWrite | 'Read and write alerts'

> [!NOTE]
> При получении маркера с помощью учетных данных пользователей:
>
> - У пользователя должно быть по крайней мере следующее разрешение на роль: "Оповещение о расследовании" (см. в рублях [Создание](user-roles.md) ролей и управление ими для получения дополнительных сведений)
> - Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).

## <a name="http-request"></a>HTTP-запрос

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>Заголовки запросов

Имя | Тип | Описание
:---|:---|:---
Authorization | Строка | Bearer {token}. **Обязательное поле**.
Content-Type | String | application/json. **Обязательное поле**.

## <a name="request-body"></a>Текст запроса

В теле запроса укажи следующие значения (все необходимые):

Свойство | Тип | Описание
:---|:---|:---
eventTime | DateTime (UTC) | Точное время события в качестве строки, полученной из продвинутой охоты. например. ```2018-08-03T16:45:21.7115183Z``` **Обязательно**.
reportId | Строка | ReportId события, полученный из продвинутой охоты. **Обязательное поле**.
machineId | Строка | Id устройства, на котором было идентифицировано событие. **Обязательное поле**.
severity | Строка | Степень серьезности оповещения. Значения свойств: "Low", "Medium" и "High". **Обязательное поле**.
title | Строка | Название для оповещений. **Обязательное поле**.
description | Строка | Описание оповещений. **Обязательное поле**.
recommendedAction| Строка | Действия, которые рекомендуется принимать сотрудником службы безопасности при анализе оповещения. **Обязательное поле**.
category| String | Категория оповещения. Значения свойств: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **required**.

## <a name="response"></a>Отклик

В случае успеха этот метод возвращает 200 [](alerts.md) ОК и новый объект оповещений в теле ответа. Если событие с указанными свойствами _(reportId,_ _eventTime_ и _machineId)_ не было найдено - 404 Не найдено.

## <a name="example"></a>Пример

### <a name="request"></a>Запрос

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
