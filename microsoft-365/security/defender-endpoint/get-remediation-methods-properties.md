---
title: Методы и свойства действий по исправлению
description: Ответ API содержит действия & устранения уязвимостей, созданные в клиенте. Вы можете запросить все действия по исправлению, только одно исправление или сведения о выставленных устройствах для выбранной задачи по исправлению.
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
ms.openlocfilehash: f720d638ec469523a1d567dee9c01fa0974b0090
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061156"
---
# <a name="remediation-activity-methods-and-properties"></a>Методы и свойства действий по исправлению

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Ответ API содержит [действия &](next-gen-threat-and-vuln-mgt.md)устранения уязвимостей, созданные   в клиенте.  

## <a name="methods"></a>Методы

Метод | Тип данных | Описание
:---|:---|:---
[Список всех действий по исправлению](get-remediation-all-activities.md) | Коллекция исследований | Возвращает сведения обо всех действиях по исправлению.
[Список выставленных устройств одного действия по исправлению](get-remediation-exposed-devices-activities.md) | Объект исследования | Возвращает сведения об выставленных устройствах для указанной активности по исправлению.
[Получить одно действие по исправлению по ID](get-remediation-one-activity.md) | Объект исследования | Возвращает сведения для указанного действия по исправлению.

Дополнительные информацию о [действиях по исправлению.](tvm-remediation.md)

## <a name="properties"></a>Свойства

ID свойства | Тип данных | Описание
:---|:---|:---
category | String | Категория действия по исправлению (конфигурация программного обеспечения и безопасности)
completerEmail | String | Если действие по исправлению было выполнено вручную кем-то, в этом столбце содержится их электронная почта.
completerId | String | Если действие по исправлению было выполнено вручную кем-то, этот столбец содержит их объектный id
completionMethod | String | Действие по исправлению может быть выполнено "автоматически" (если все устройства исправлены) или "вручную" человеком, который выбирает "метку как завершенную".
createdOn | DateTime | Время создания этого действия по исправлению
description | String | Описание этого действия по исправлению
dueOn | DateTime | Дата, установленная создателем для этого действия по исправлению
fixedDevices |  | Количество исправленных устройств
id | String | ID этого действия по исправлению
nameId | String | Связанное имя продукта
priority | String | Приоритет, установленный создателем для этого действия по исправлению (High\Medium\Low)
productId | String | Соответствующий ID продукта
productivityImpactRemediationType | String | Несколько изменений конфигурации можно запросить только для устройств без влияния пользователя. Это значение указывает на выбор между "всеми выставленными устройствами" или "только устройствами без влияния пользователя".
rbacGroupNames | String | Связанные имена групп устройств
recommendedProgram | String | Рекомендуемая программа для обновления до
recommendedVendor | String | Рекомендуемый поставщик для обновления до
recommendedVersion | String | Рекомендуемая версия для обновления и обновления до
relatedComponent | String | Связанный компонент этого действия по исправлению (аналогичный связанному компоненту для рекомендации по безопасности)
requesterEmail | String | Адрес электронной почты создателя
requesterId | String | ID объекта Creator
requesterNotes | String | Заметки (бесплатный текст), добавленные создателем для этого действия по исправлению
scid | String | SCID связанной рекомендации по безопасности
status | String | Состояние действия по исправлению (Active/Completed)
statusLastModifiedOn | DateTime | Дата обновления поля состояния
targetDevices | Длинное целое | Количество открытых устройств, к которые применяется это исправление
title | String | Название этого действия по исправлению
type | String | Тип устранения
vendorId | String | Имя связанного поставщика

## <a name="see-also"></a>См. также

- [Получить одно действие по исправлению по ID](get-remediation-one-activity.md)

- [Список всех действий по исправлению](get-remediation-all-activities.md)

- [Список выставленных устройств одного действия по исправлению](get-remediation-exposed-devices-activities.md)

- [Управление рисками & уязвимостей](next-gen-threat-and-vuln-mgt.md)

- [Уязвимости в организации](tvm-weaknesses.md)
