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
ms.technology: mde
ms.openlocfilehash: 4c0ecd89c45ec2c91dc37f0c9cd0bfb868c0474e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245544"
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
completerEmail | Строка | Если действие по исправлению было выполнено вручную кем-то, в этом столбце содержится их электронная почта.
completerId | Строка | Если действие по исправлению было выполнено вручную кем-то, этот столбец содержит их объектный id
completionMethod | Строка | Действие по исправлению может быть выполнено "автоматически" (если все устройства исправлены) или "вручную" человеком, который выбирает "метку как завершенную".
createdOn | DateTime | Время создания этого действия по исправлению
description | Строка | Описание этого действия по исправлению
dueOn | DateTime | Дата, установленная создателем для этого действия по исправлению
fixedDevices |  | Количество исправленных устройств
id | Строка | ID этого действия по исправлению
nameId | Строка | Связанное имя продукта
priority | Строка | Приоритет, установленный создателем для этого действия по исправлению (High\Medium\Low)
productId | Строка | Соответствующий ID продукта
productivityImpactRemediationType | Строка | Несколько изменений конфигурации можно запросить только для устройств без влияния пользователя. Это значение указывает на выбор между "всеми выставленными устройствами" или "только устройствами без влияния пользователя".
rbacGroupNames | Строка | Связанные имена групп устройств
recommendedProgram | Строка | Рекомендуемая программа для обновления до
recommendedVendor | Строка | Рекомендуемый поставщик для обновления до
recommendedVersion | Строка | Рекомендуемая версия для обновления и обновления до
relatedComponent | Строка | Связанный компонент этого действия по исправлению (аналогичный связанному компоненту для рекомендации по безопасности)
requesterEmail | Строка | Адрес электронной почты создателя
requesterId | Строка | ID объекта Creator
requesterNotes | Строка | Заметки (бесплатный текст), добавленные создателем для этого действия по исправлению
scid | Строка | SCID связанной рекомендации по безопасности
status | String | Состояние действия по исправлению (Active/Completed)
statusLastModifiedOn | DateTime | Дата обновления поля состояния
targetDevices | Длинное целое | Количество открытых устройств, к которые применяется это исправление
title | Строка | Название этого действия по исправлению
type | Строка | Тип устранения
vendorId | Строка | Имя связанного поставщика

## <a name="see-also"></a>См. также

- [Получение одного действия по исправлению по ИД](get-remediation-one-activity.md)

- [Перечисление всех действий по исправлению](get-remediation-all-activities.md)

- [Перечисление устройств, затрагиваемых одним действием по исправлению](get-remediation-exposed-devices-activities.md)

- [Риск на основе угрозы & управление уязвимостями](next-gen-threat-and-vuln-mgt.md)

- [Уязвимости в организации](tvm-weaknesses.md)
