---
title: Управление Защитником Майкрософт для конечной точки с помощью диспетчера конфигурации
description: Узнайте, как управлять Microsoft Defender для конечной точки с помощью диспетчера конфигурации
keywords: после переноса, управления, операций, обслуживания, использования, Диспетчер конфигурации, защита от угроз защитника Windows, atp, edr
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
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 36599d830ac737b112df9f7c948e65829d6a7ce6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074877"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Управление Защитником Майкрософт для конечной точки с помощью диспетчера конфигурации

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Рекомендуется использовать Microsoft [Endpoint Manager](https://docs.microsoft.com/mem), который включает [Microsoft Intune (Intune)](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) и [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) (Configuration Manager) для управления функциями защиты от угроз для устройств (также именуемой конечными точками). 
- [Дополнительные дополнительные информацию о диспетчере конечных точек](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [Совместное управление Microsoft Defender для конечной точки на устройствах Windows 10 с помощью configuration Manager и Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Настройка Microsoft Defender для конечной точки с помощью диспетчера конфигурации

|Задача  |Дополнительные ресурсы  |
|---------|---------|
|**Установите консоль Configuration Manager,** если она еще не имеется.<br/><br/>*Если у вас еще нет консоли Configuration Manger, используйте эти ресурсы для получения битов и ее установки.* |[Получить носители установки](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Установка консоли Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Использование диспетчера конфигурации для бортовых устройств** в Microsoft Defender для конечной точки <br/><br/> *Если у вас есть устройства (или конечные точки), которые еще не были на борту в Microsoft Defender для конечной точки, вы можете сделать это с помощью Configuration Manager.*   |[Onboard to Microsoft Defender for Endpoint with Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Управление политиками антивирусного обеспечения и безопасностью брандмауэра Windows** для клиентских компьютеров (конечных точек)<br/><br/>*Настройте функции защиты конечной точки, включая Microsoft Defender для endpoint, защиту от эксплойтов, управление приложениями, антивирусное программное обеспечение, параметры брандмауэра и т. д.*  |[Диспетчер конфигурации: защита конечных точек](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Выбор методов обновления обновлений антивирусных программ** на устройствах организации <br/><br/>*С помощью endpoint Protection in Configuration Manager вы можете выбрать один из нескольких методов, чтобы сохранить определения противомалярийных программ на устройствах организации.* |[Настройка обновлений определения для защиты конечных точек](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Использование диспетчера конфигурации для доставки обновлений определений](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Включить защиту сети,** чтобы предотвратить использование сотрудниками приложений с вредоносным контентом в Интернете <br/><br/>*Сначала рекомендуется использовать [режим аудита](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) для защиты сети в тестовой среде, чтобы узнать, какие приложения будут заблокированы перед развертыванием.* |[Включив защиту сети с помощью диспетчера конфигурации](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Настройка управляемого доступа к папкам для** защиты от программ-вымогателей <br/><br/>*Управляемый доступ к папкам также называется защитой от антивирусных программ.*   |[Защита конечной точки: доступ к управляемой папке](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Включить управляемый доступ к папкам в Microsoft Endpoint Configuration Manage](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Настройка центра безопасности Microsoft Defender

Если вы еще этого не сделали, настройте центр безопасности **Microsoft Defender** Для просмотра оповещений, настройки функций защиты от угроз и просмотра подробных сведений об общей позиции безопасности [https://securitycenter.windows.com](https://securitycenter.windows.com) организации. 

Вы также можете настроить, можно ли и какие функции конечные пользователи могут видеть в Центре безопасности Microsoft Defender.

- [Обзор Центра безопасности Защитника Майкрософт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Защита конечной точки: Центр безопасности Защитника Майкрософт](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Дальнейшие действия

- [Обзор управления угрозами и уязвимостью](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Посетите панель мониторинга операций безопасности Центра безопасности Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Управление microsoft Defender для конечной точки с помощью Intune](manage-atp-post-migration-intune.md)
