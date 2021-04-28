---
title: Список всех действий по исправлению
description: Возвращает сведения обо всех действиях по исправлению.
keywords: apis, remediation, remediation api, get, remediation tasks,
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
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061161"
---
# <a name="list-all-remediation-activities"></a>Список всех действий по исправлению

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

**Сведения о свойствах**

Свойство (id) | Тип данных | Описание | Пример возвращенного значения
:---|:---|:---|:---
category | String | Категория действия по исправлению (конфигурация программного обеспечения и безопасности) | Программное обеспечение
completerEmail | String | Если действие по исправлению было выполнено вручную кем-то, в этом столбце содержится их электронная почта. | null
completerId | String | Если действие по исправлению было выполнено вручную кем-то, этот столбец содержит их объектный id | null
completionMethod | String | Действие по исправлению может быть выполнено "автоматически" (если все устройства исправлены) или "вручную" человеком, который выбирает "метку как завершенную" | Автоматически
createdOn | DateTime | Время создания этого действия по исправлению | 2021-01-12T18:54:11.5499478Z
description | String | Описание этого действия по исправлению | Обновите Chrome в более поздней версии, чтобы устранить 1248 известных уязвимостей, затрагивающих устройства.
dueOn | DateTime | Дата, установленная создателем для этого действия по исправлению | 2021-01-13T00:00:00Z
fixedDevices | . | Количество исправленных устройств | 2
id | String | ID этого действия по исправлению | 097d9735-5479-4899-b1b7-77398899df92
nameId | String | Связанное имя продукта | chrome
priority | String | Приоритет, установленный создателем для этого действия по исправлению (High\Medium\Low) | Высокая
productId | String | Соответствующий ID продукта | Google-_-chrome
productivityImpactRemediationType | String | Несколько изменений конфигурации можно запросить только для устройств без влияния пользователя. Это значение указывает на выбор между "всеми выставленными устройствами" или "только устройствами без влияния пользователя". | AllExposedAssets
rbacGroupNames | String | Связанные имена групп устройств | [ "Windows Servers", "Windows 10" ]
recommendedProgram | String | Рекомендуемая программа для обновления до | null
recommendedVendor | String | Рекомендуемый поставщик для обновления до | null
recommendedVersion | String | Рекомендуемая версия для обновления и обновления до | null
relatedComponent | String | Связанный компонент этого действия по исправлению (аналогичный связанному компоненту для рекомендации по безопасности) | Google Chrome
requesterEmail | String | Адрес электронной почты создателя | globaladmin@UserName.contoso.com
requesterId | String | ID объекта Creator | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | String | Заметки (бесплатный текст), добавленные создателем для этого действия по исправлению | null
scid | String | SCID связанной рекомендации по безопасности | null
status | String | Состояние действия по исправлению (Active/Completed) | Активное
statusLastModifiedOn | DateTime | Дата обновления поля состояния | 2021-01-12T18:54:11.5499487Z
targetDevices | Длинное целое | Количество открытых устройств, к которые применяется это исправление | 43
title | String | Название этого действия по исправлению | Обновление Google Chrome
type | String | Тип устранения | Update
vendorId | String | Имя связанного поставщика | Google

## <a name="example"></a>Пример

**Пример запроса**

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

**Пример ответа**

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

- [Получить одно действие по исправлению по ID](get-remediation-one-activity.md)

- [Список выставленных устройств одного действия по исправлению](get-remediation-exposed-devices-activities.md)

- [Управление рисками & уязвимостей](next-gen-threat-and-vuln-mgt.md)

- [Уязвимости в организации](tvm-weaknesses.md)
