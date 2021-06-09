---
title: Необходимые & разрешения - контроль угроз и уязвимостей
description: Прежде чем приступить к контроль угроз и уязвимостей, убедитесь, что у вас есть соответствующие конфигурации и разрешения.
keywords: условия & управление уязвимостями разрешений, контроль угроз и уязвимостей разрешений, необходимые для разрешения Microsoft Defender для конечных точек TVM, управление уязвимостями
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843954"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Необходимые & разрешения - контроль угроз и уязвимостей

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Угроза и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Убедитесь, что ваши устройства:

- Находятся на борту в Microsoft Defender для конечной точки
- Запуск [поддерживаемых операционных систем и платформ](tvm-supported-os.md)
- Установить и развернуть в сети следующие обязательные обновления, чтобы повысить уровень обнаружения уязвимостей:

> Выпуск | Номер и ссылка обновления безопасности
> :---|:---
> Windows 10 Версия 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) и [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10 Версия 1803 | [KB4493464](https://support.microsoft.com/help/4493464) и [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10 Версия 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10 Версия 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- На борту находятся [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) [и Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) чтобы помочь устранять угрозы, найденные контроль угроз и уязвимостей. Если используется диспетчер конфигурации, обновите консоль до последней версии.
    - **Примечание.** Если включено подключение Intune, можно создать задачу безопасности Intune при создании запроса на исправление. Этот параметр не появится, если подключение не установлено.
- Есть по крайней мере одна рекомендация по безопасности, которую можно просмотреть на странице устройства
- Помечены или помечены как совместно управляемые

## <a name="relevant-permission-options"></a>Соответствующие параметры разрешений

1. Войдите Центр безопасности в Microsoft Defender учетную запись с помощью администратора безопасности или роли глобального администратора.
2. В области навигации выберите **Параметры > роли**.

Дополнительные сведения см. в дополнительных сведениях о создании и [управлении ролями для](user-roles.md) управления доступом на основе ролей

### <a name="view-data"></a>Просмотр данных

- **Операции безопасности** — просмотр всех данных операций безопасности на портале
- **Угроза и управление уязвимостями** — просмотр контроль угроз и уязвимостей данных на портале

### <a name="active-remediation-actions"></a>Активные действия по исправлению

- **Операции безопасности** . Принятие ответных действий, утверждение или отклонение в ожидании действий по исправлению, управление разрешенными и заблокированными списками для автоматизации и индикаторов
- **Обработка управление уязвимостями** и управление уязвимостями - Создание новых исключений и управление активными исключениями
- **Обработка угроз и управление уязвимостями -** Отправка новых запросов на исправление, создание билетов и управление существующими действиями по исправлению

Дополнительные сведения см. в [параметрах разрешений RBAC](user-roles.md#permission-options)

## <a name="related-articles"></a>Связанные статьи

- [Обзор угроз и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Поддерживаемые операционные системы и платформы](tvm-supported-os.md)
- [Назначение значения устройства](tvm-assign-device-value.md)
- [Панель мониторинга угроз и управление уязвимостями](tvm-dashboard-insights.md)

