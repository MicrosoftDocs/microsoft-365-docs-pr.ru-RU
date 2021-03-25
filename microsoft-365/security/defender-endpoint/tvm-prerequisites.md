---
title: Необходимые & разрешения — управление угрозами и уязвимостью
description: Прежде чем приступить к использованию управления угрозами и уязвимостями, убедитесь, что у вас есть соответствующие конфигурации и разрешения.
keywords: Необходимые & управления уязвимостями, необходимые для управления разрешениями на угрозы и уязвимости, предварительные условия разрешений MDATP TVM, управление уязвимостями
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ca095a7a65a114182d736176840fdd4e651a8646
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074845"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Необходимые & разрешения — управление угрозами и уязвимостью

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Управление угрозами и уязвимостями](next-gen-threat-and-vuln-mgt.md)
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

- Вы можете воспользоваться службами [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) и  [Microsoft Endpoint Configuration Manager,](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) чтобы помочь устранять угрозы, найденные в управлении угрозами и уязвимостями. Если используется диспетчер конфигурации, обновите консоль до последней версии.
    - **Примечание.** Если включено подключение Intune, можно создать задачу безопасности Intune при создании запроса на исправление. Этот параметр не появится, если подключение не установлено.
- Есть по крайней мере одна рекомендация по безопасности, которую можно просмотреть на странице устройства
- Помечены или помечены как совместно управляемые

## <a name="relevant-permission-options"></a>Соответствующие параметры разрешений

1. Войдите в Центр безопасности Microsoft Defender с помощью учетной записи с администратором безопасности или ролью глобального администратора.
2. В области навигации выберите **Параметры > ролей**.

Дополнительные сведения см. в дополнительных сведениях о создании и [управлении ролями для](user-roles.md) управления доступом на основе ролей

### <a name="view-data"></a>Просмотр данных

- **Операции безопасности** — просмотр всех данных операций безопасности на портале
- **Управление угрозами и уязвимостью** — просмотр данных управления угрозами и уязвимостей на портале

### <a name="active-remediation-actions"></a>Активные действия по исправлению

- **Операции безопасности** . Принятие ответных действий, утверждение или отклонение в ожидании действий по исправлению, управление разрешенными и заблокированными списками для автоматизации и индикаторов
- **Управление угрозами и уязвимостями — обработка исключений** — создание новых исключений и управление активными исключениями
- **Управление угрозами** и уязвимостью — обработка исправлений — отправка новых запросов на исправление, создание билетов и управление существующими действиями по исправлению.

Дополнительные сведения см. в [параметрах разрешений RBAC](user-roles.md#permission-options)

## <a name="related-articles"></a>Связанные статьи

- [Обзор управления угрозами и уязвимостью](next-gen-threat-and-vuln-mgt.md)
- [Поддерживаемые операционные системы и платформы](tvm-supported-os.md)
- [Назначение значения устройства](tvm-assign-device-value.md)
- [Панель мониторинга управления угрозами и уязвимостью](tvm-dashboard-insights.md)

