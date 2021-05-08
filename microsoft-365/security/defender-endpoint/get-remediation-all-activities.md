---
title: Перечисление всех действий по исправлению
description: Возвращает сведения обо всех действиях по исправлению.
keywords: apis, remediation, remediation api, get, remediation tasks, all remediation,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cf7c79cb6cc76af88ce0293a013ba6edbf435d8c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245496"
---
# <a name="list-all-remediation-activities"></a>Перечисление всех действий по исправлению

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Описание API

Возвращает сведения обо всех действиях по исправлению.

[Дополнительные информацию о действиях по исправлению.](tvm-remediation.md)

**URL-адрес:** GET: /api/remediationTasks

## <a name="permissions"></a>Разрешения

Для вызова этого API требуется одно из следующих разрешений. Дополнительные сведения, в том числе о выборе разрешений, см. в материале [Use Microsoft Defender for Endpoint API.](apis-intro.md)

Тип разрешения | Разрешение | Имя отображения разрешений
:---|:---|:---
Для приложений | RemediationTask.Read.All | \'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'
Делегированные (рабочая или учебная учетная запись) | RemediationTask.Read.Read | \'Чтение сведений об уязвимостях управления угрозами и уязвимостью\'

## <a name="properties"></a>Свойства

Свойство (id) | Тип данных | Описание | Пример возвращенного значения
:---|:---|:---|:---
category | String | Категория действия по исправлению (конфигурация программного обеспечения и безопасности) | Программное обеспечение
completerEmail | Строка | Если действие по исправлению было выполнено вручную кем-то, в этом столбце содержится их электронная почта. | null
completerId | Строка | Если действие по исправлению было выполнено вручную кем-то, этот столбец содержит их объектный id | null
completionMethod | Строка | Действие по исправлению может быть выполнено "автоматически" (если все устройства исправлены) или "вручную" человеком, который выбирает "метку как завершенную" | Автоматически
createdOn | DateTime | Время создания этого действия по исправлению | 2021-01-12T18:54:11.5499478Z
description | Строка | Описание этого действия по исправлению | Обновите Microsoft Silverlight в более поздней версии, чтобы устранить известные уязвимости, влияющие на устройства.
dueOn | DateTime | Дата, установленная создателем для этого действия по исправлению | 2021-01-13T00:00:00Z
fixedDevices | . | Количество исправленных устройств | 2
id | Строка | ID этого действия по исправлению | 097d9735-5479-4899-b1b7-77398899df92
nameId | Строка | Связанное имя продукта | Microsoft Silverlight
priority | Строка | Приоритет, установленный создателем для этого действия по исправлению (High\Medium\Low) | Высокий
productId | Строка | Соответствующий ID продукта | microsoft-__-silverlight
productivityImpactRemediationType | Строка | Несколько изменений конфигурации можно запросить только для устройств без влияния пользователя. Это значение указывает на выбор между "всеми выставленными устройствами" или "только устройствами без влияния пользователя". | AllExposedAssets
rbacGroupNames | Строка | Связанные имена групп устройств | [ "Windows Серверы", "Windows 10" ]
recommendedProgram | Строка | Рекомендуемая программа для обновления до | null
recommendedVendor | Строка | Рекомендуемый поставщик для обновления до | null
recommendedVersion | Строка | Рекомендуемая версия для обновления и обновления до | null
relatedComponent | Строка | Связанный компонент этого действия по исправлению (аналогичный связанному компоненту для рекомендации по безопасности) | Microsoft Silverlight
requesterEmail | Строка | Адрес электронной почты создателя | globaladmin@UserName.contoso.com
requesterId | Строка | ID объекта Creator | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | Строка | Заметки (бесплатный текст), добавленные создателем для этого действия по исправлению | null
scid | Строка | SCID связанной рекомендации по безопасности | null
status | String | Состояние действия по исправлению (Active/Completed) | Активное
statusLastModifiedOn | DateTime | Дата обновления поля состояния | 2021-01-12T18:54:11.5499487Z
targetDevices | Длинное целое | Количество открытых устройств, к которые применяется это исправление | 43
title | Строка | Название этого действия по исправлению | Обновление Microsoft Silverlight
type | Строка | Тип устранения | Update
vendorId | Строка | Имя связанного поставщика | Корпорация Майкрософт

## <a name="example"></a>Пример

### <a name="request-example"></a>Пример запроса

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a>Пример ответа

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a>См. также

- [Методы и свойства по исправлению](get-remediation-methods-properties.md)

- [Получение одного действия по исправлению по ИД](get-remediation-one-activity.md)

- [Перечисление устройств, затрагиваемых одним действием по исправлению](get-remediation-exposed-devices-activities.md)

- [Риск на основе угрозы & управление уязвимостями](next-gen-threat-and-vuln-mgt.md)

- [Уязвимости в организации](tvm-weaknesses.md)
