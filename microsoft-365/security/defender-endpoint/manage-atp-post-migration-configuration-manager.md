---
title: Управление Защитником Майкрософт для конечной точки с помощью диспетчера конфигурации
description: Узнайте, как управлять Microsoft Defender для конечной точки с помощью диспетчера конфигурации
keywords: после переноса, управления, операций, обслуживания, использования, диспетчера конфигурации, Microsoft Defender для конечной точки, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: 5fde3bfad69a5851dd94b76afb262f8be12d0360
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908261"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Управление Защитником Майкрософт для конечной точки с помощью диспетчера конфигурации

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Рекомендуется использовать [Microsoft Endpoint Manager,](/mem)который включает Microsoft Intune [](/mem/intune/fundamentals/what-is-intune) (Intune) и [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) для управления функциями защиты от угроз организации для устройств (также именуемой конечными точками). 
- [Дополнительные дополнительные Endpoint Manager](/mem/endpoint-manager-overview)
- [Совместное управление Microsoft Defender для конечной точки на Windows 10 устройствах с помощью Configuration Manager и Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Настройка Microsoft Defender для конечной точки с помощью диспетчера конфигурации

|Задача  |Дополнительные ресурсы  |
|---------|---------|
|**Установите консоль Configuration Manager,** если она еще не имеется.<br/><br/>*Если у вас еще нет консоли Configuration Manger, используйте эти ресурсы для получения битов и ее установки.* |[Получить носители установки](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Установка консоли Configuration Manager](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Использование диспетчера конфигурации для бортовых устройств** в Microsoft Defender для конечной точки <br/><br/> *Если у вас есть устройства (или конечные точки), которые еще не были на борту в Microsoft Defender для конечной точки, вы можете сделать это с помощью Configuration Manager.*   |[Onboard to Microsoft Defender for Endpoint with Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Управление политиками и** безопасностью Windows брандмауэра для клиентских компьютеров (конечных точек)<br/><br/>*Настройте функции защиты конечной точки, включая Microsoft Defender для endpoint, защиту от эксплойтов, управление приложениями, антивирусное программное обеспечение, параметры брандмауэра и т. д.*  |[Диспетчер конфигурации: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Выбор методов обновления обновлений антивирусных программ** на устройствах организации <br/><br/>*С Endpoint Protection в Configuration Manager можно выбрать один из нескольких методов, чтобы сохранить определения противомалярийных программ в курсе на устройствах организации.* |[Настройка обновлений определения для Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Использование диспетчера конфигурации для доставки обновлений определений](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Включить защиту сети,** чтобы предотвратить использование сотрудниками приложений с вредоносным контентом в Интернете <br/><br/>*Сначала рекомендуется использовать [режим аудита](/microsoft-365/security/defender-endpoint/evaluate-network-protection) для защиты сети в тестовой среде, чтобы узнать, какие приложения будут заблокированы перед развертыванием.* |[Включив защиту сети с помощью диспетчера конфигурации](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Настройка управляемого доступа к папкам для** защиты от программ-вымогателей <br/><br/>*Управляемый доступ к папкам также называется защитой от антивирусных программ.*   |[Защита конечной точки: доступ к управляемой папке](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Включить управляемый доступ к папкам в Microsoft Endpoint Configuration Manage](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Настройка Центр безопасности в Microsoft Defender

Если этого еще не сделано, настройте портал Microsoft 365 Defender для просмотра оповещений, настройки функций защиты от угроз и просмотра подробных сведений об общей позиции безопасности организации. См. [Центр безопасности в Microsoft Defender](microsoft-defender-security-center.md). Вы также можете настроить, можно ли и какие функции конечные пользователи могут видеть на портале Microsoft 365 Defender.

- [Обзор Центр безопасности в Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Защита конечных точек: Центр безопасности в Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Дальнейшие действия

- [Получите обзор контроль угроз и уязвимостей](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Посетите панель мониторинга Центр безопасности в Microsoft Defender операций безопасности](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Управление microsoft Defender для конечной точки с помощью Intune](manage-atp-post-migration-intune.md)
