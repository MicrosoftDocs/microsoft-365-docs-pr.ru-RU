---
title: Развертывание защиты от угроз сетевой безопасности в Microsoft 365
description: Узнайте, как развернуть службы защиты от угроз и возможности ИТ-безопасности сети в Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 79352aca2012e6615f41b19f4a77fc5cf125f4c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926754"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Развертывание возможностей защиты от угроз в Microsoft 365

[Вредоносные](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)программы и сложные кибератаки, такие как угрозы без [файлов,](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)являются распространенным событием. Предприятиям необходимо защитить себя и своих клиентов с помощью эффективных возможностей ИТ-безопасности сети. Такие атаки могут привести к серьезным проблемам в организации, от потери доверия до финансовых проблем, простоев в организации и т. д. Защита от угроз имеет важное значение, но может быть сложно определить, куда следует сосредоточить время, усилия и ресурсы организации. 

Решения для обеспечения безопасности Майкрософт встроены в наши продукты и службы. Возможности автоматизации и машинного обучения снижают нагрузку на группы безопасности, чтобы убедиться, что нужные элементы будут рассмотрены. Кроме того, преимущества решений по обеспечению сетевой безопасности Корпорации Майкрософт построены на том, что мы ежедневно обработать сигналы в [intelligent Security Graph.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph) Решения для обеспечения безопасности [Microsoft 365 включают Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), решение, которое объединяет сигналы в вашей электронной почте, данных, устройствах и удостоверениях, чтобы нарисовать изображение сложных угроз для вашей организации.


Обзор процесса развертывания показан в приведенном ниже видео.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Используйте эту статью в качестве руководства по реализации решения для защиты от угроз.

## <a name="threat-protection-in-microsoft-365-e5"></a>Защита от угроз в Microsoft 365 E5

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) позволяет защитить организацию с помощью адаптивной встроенной аналитики. С помощью функций защиты от угроз в Microsoft 365 E5 вы можете обнаруживать и исследовать сложные угрозы, скомпрометированную личность и вредоносные действия в локальной и облачной среде.

В Microsoft 365 E5 возможности защиты от угроз интегрированы по умолчанию. Сигналы от каждой возможности добавляют силы в общую способность обнаруживать угрозы и реагировать на них. Объединенный набор возможностей обеспечивает лучшую защиту для организаций, особенно для нескольких национальных организаций, по сравнению с запуском продуктов, не в корпорации Майкрософт. На следующем рисунке показаны службы и возможности защиты от угроз в Microsoft 365 E5, описанные в этой статье.

![Обзор Защитника Microsoft 365](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Как только вы развернете любую из возможностей Защитника Office 365, вы можете включить Microsoft 365 Defender, который объединяет сигналы и данные в одном месте. 

![Концептуальная иллюстрация панели мониторинга Защитника Microsoft 365](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

На следующем рисунке показан рекомендуемый путь для развертывания этих отдельных возможностей. 

![Сигналы защиты от угроз M365](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Решение и возможности  |Описание  |
|---------|---------|
|Многофакторная проверка подлинности и условный доступ     |Защита от компрометации удостоверений и устройств. Начните с этой защиты, так как она является основой. Конфигурация, рекомендованная в этом руководстве, включает в себя защиту идентификации Azure AD в качестве обязательного условия.     |
|Microsoft Defender для удостоверений     |  Облачное решение для обеспечения безопасности, которое использует сигналы локальной службы Active Directory для идентификации, обнаружения и изучения сложных угроз, скомпрометенных удостоверений и вредоносных действий внутри организации. Теперь сосредоточьте внимание на Microsoft Defender на удостоверении, так как он защищает вашу облачную инфраструктуру и вашу облачную инфраструктуру, не имеет зависимостей и необходимых условий и может обеспечить немедленные преимущества.       | 
|Microsoft Defender для Office 365     | Защищает организацию от вредоносных угроз, создаваемых электронными сообщениями, ссылками (URL-адресами) и средствами совместной работы. Защита от вредоносных программ, фишинга, спуфинга и других типов атак. Далее рекомендуется настроить Microsoft Defender для Office 365, так как управление изменениями, перенос параметров из системы управления и другие аспекты могут занять больше времени. <br><br>Примечание. Настройте возможности защиты от угроз, включенные во все подписки на Office 365 (Exchange Online Protection).       |
|Microsoft Defender для конечной точки    | Платформа защиты конечных точек, помогая предотвращать, обнаруживать, исследовать и реагировать на сложные угрозы.  Развертывание Защитника для конечной точки может занять некоторое время, но настройка может быть сделана параллельно с другими возможностями.   |
|Microsoft Cloud App Security     |   Брокер безопасности облачного доступа для обнаружения, исследования и управления. Вы можете включить Microsoft Cloud App Security на ранних стадиях сбора данных и статистики. Реализация информации и другой целевой защиты в приложениях SaaS включает планирование и может занять больше времени.       | 

> [!TIP]
> Организации с несколькими группами безопасности могут реализовать эти возможности параллельно.

## <a name="deploy-your-threat-protection-solution"></a>Развертывание решения для защиты от угроз

Чтобы убедиться, что ваша организация обладает наилучшей защитой, необходимо настроить и развернуть решение для обеспечения безопасности, включив в него следующие действия:

1. [Настройка многофакторной проверки подлинности и политик условного доступа](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Настройка Microsoft Defender для удостоверений](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Включить Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Настройка Защитника для Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Настройка Microsoft Defender для конечной точки](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Настройка Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Отслеживание состояния и действия](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Обучение пользователей](deploy-threat-protection-configure.md#step-8-train-users)

Функции защиты от угроз можно настроить параллельно, поэтому если за различные службы отвечает несколько групп безопасности сети, они могут одновременно настраивать функции защиты в организации. На следующей схеме показано высокоуровневый процесс развертывания возможностей защиты от угроз. 

![Процесс развертывания возможностей защиты от угроз](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 
