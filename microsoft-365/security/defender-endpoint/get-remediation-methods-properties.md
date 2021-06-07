---
title: Методы и свойства действий по исправлению
description: Ответ API содержит действия по исправлению & управление уязвимостями, созданные в клиенте. Вы можете запросить все действия по исправлению, только одно исправление или сведения о выставленных устройствах для выбранной задачи по исправлению.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation methods, remediation properties,
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 67009961ecc3755b5af21b2e773bc817ea46bec0
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769241"
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

Ответ API содержит [действия & управление уязвимостями](next-gen-threat-and-vuln-mgt.md)угрозы, созданные   в клиенте.  

## <a name="methods"></a>Методы

Метод | Тип данных | Описание
:---|:---|:---
[Перечисление всех действий по исправлению](get-remediation-all-activities.md) | Коллекция исследований | Возвращает сведения обо всех действиях по исправлению.
[Перечисление устройств, затрагиваемых одним действием по исправлению](get-remediation-exposed-devices-activities.md) | Объект исследования | Возвращает сведения об выставленных устройствах для указанной активности по исправлению.
[Получение одного действия по исправлению по ИД](get-remediation-one-activity.md) | Объект исследования | Возвращает сведения для указанного действия по исправлению.

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

- [Получение одного действия по исправлению по ИД](get-remediation-one-activity.md)

- [Перечисление всех действий по исправлению](get-remediation-all-activities.md)

- [Перечисление устройств, затрагиваемых одним действием по исправлению](get-remediation-exposed-devices-activities.md)

- [Риск на основе угрозы & управление уязвимостями](next-gen-threat-and-vuln-mgt.md)

- [Уязвимости в организации](tvm-weaknesses.md)
