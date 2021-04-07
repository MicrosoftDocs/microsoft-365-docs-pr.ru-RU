---
title: Развертывание возможностей защиты от угроз в Microsoft 365
description: Обзор служб защиты от угроз и безопасности в Microsoft 365 E5.
keywords: защита от угроз, безопасность, E5, кибератака, вредоносные программы, M365, решение
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: Admin
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 922e7b7ea8bceced7085af49485b3479a671d5cd
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599963"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>Развертывание возможностей защиты от угроз в Microsoft 365 E5

[Вредоносные](/windows/security/threat-protection/intelligence/understanding-malware)программы и сложные кибератаки, такие как [угрозы](/windows/security/threat-protection/intelligence/fileless-threats)без файлов, являются распространенным явлением. Предприятиям необходимо защитить себя и своих клиентов эффективными возможностями ИТ-безопасности. Кибератаки могут вызвать серьезные проблемы для организации, начиная от потери доверия до финансовых проблем, простоев, угрожающих бизнесу, и т. д. Защита от угроз имеет важное значение, но может быть сложно определить, где сосредоточить время, усилия и ресурсы организации. 

Решения для обеспечения безопасности Майкрософт встроены в наши продукты и службы. Возможности автоматизации и машинного обучения уменьшают нагрузку на группы безопасности, чтобы убедиться, что нужные элементы будут устранены. А сила решений microsoft security построена на триллионах сигналов, которые мы обработать каждый день в нашем [интеллектуальном графике безопасности.](/graph/security-concept-overview) Решения для безопасности Microsoft [365 включают Microsoft 365 Defender](../security/defender/microsoft-365-defender.md), решение, которое объединяет сигналы по электронной почте, данным, устройствам и удостоверениям, чтобы нарисовать картину расширенных угроз в отношении вашей организации.

Обзор процесса развертывания показан в приведенном ниже видео.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]


## <a name="threat-protection-in-microsoft-365-e5"></a>Защита от угроз в Microsoft 365 E5

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) позволяет защитить организацию адаптивным встроенным интеллектом. С помощью функций защиты от угроз в Microsoft 365 E5 можно обнаруживать и исследовать расширенные угрозы, скомпрометированную идентификацию и вредоносные действия в локальной и облачной среде.

В Microsoft 365 E5 возможности защиты от угроз интегрированы по умолчанию. Сигналы от каждой возможности добавляют силу общей способности обнаруживать угрозы и реагировать на них. Комбинированный набор возможностей обеспечивает лучшую защиту для организаций, особенно многонациональных организаций, по сравнению с запуском продуктов, не в microsoft. На следующем изображении показаны службы и возможности защиты от угроз в Microsoft 365 E5, описанные в этой статье.

![Обзор защитника Microsoft 365](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 Defender объединяет сигналы и данные в единый центр безопасности [Microsoft 365.](/microsoft-365/security/defender/overview-security-center) 

![Концептуальная иллюстрация панели мониторинга Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

На следующей иллюстрации показан рекомендуемый путь для развертывания этих отдельных возможностей. 

![Сигналы защиты от угроз M365](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|Решение/возможности  |Описание  |
|---------|---------|
|Многофакторная проверка подлинности и условный доступ     |Защита от скомпрометированных удостоверений и устройств. Начните с этой защиты, так как она является фундаментальной. Рекомендуемая в этом руководстве конфигурация включает в себя защиту удостоверений Azure AD в качестве обязательного условия.     |
|Microsoft Defender для удостоверений     |  Облачное решение безопасности, которое использует локальное решение Active Directory Domain Services (AD DS) для выявления, обнаружения и расследования расширенных угроз, скомпрометированных удостоверений и вредоносных действий инсайдеров, направленных на организацию. Сосредоточься на Microsoft Defender для identity далее, так как он защищает локальной и облачной инфраструктуры, не имеет зависимостей и необходимых условий и может обеспечить немедленные преимущества для безопасности. | 
|Microsoft Defender для Office 365     | Защищает организацию от вредоносных угроз, создаваемых электронными сообщениями, ссылками (URL-адресами) и средствами совместной работы. Защита от вредоносных программ, фишинга, спуфинга и других типов атак. Настройка Microsoft Defender для Office 365 рекомендуется далее, так как управление изменениями, перенос параметров из действующей системы и другие соображения могут занять больше времени для развертывания. <p>**ПРИМЕЧАНИЕ.** Убедитесь, что необходимо настроить возможности защиты от угроз, включенные во все подписки Office 365 (Exchange Online Protection).       |
|Microsoft Defender для конечной точки    | Платформа защиты конечной точки, которая помогает предотвращать, обнаруживать, исследовать и реагировать на расширенные угрозы.  Развертывание Defender для Конечной точки может занять некоторое время, но конфигурация может быть сделана параллельно с другими возможностями.   |
|Microsoft Cloud App Security     |   Брокер по безопасности облачного доступа для обнаружения, расследования и управления. Вы можете включить microsoft Cloud App Security на ранних стадиях для начала сбора данных и данных. Реализация информации и другой адресной защиты в приложениях SaaS включает планирование и может занять больше времени.       | 

> [!TIP]
> Организации с несколькими группами безопасности могут реализовать эти возможности параллельно. 

## <a name="deploy-your-threat-protection-solution"></a>Развертывание решения по защите от угроз

 Следующая схема иллюстрирует процесс развертывания возможностей защиты от угроз на высоком уровне. 

![Процесс развертывания возможностей защиты от угроз](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Чтобы убедиться, что ваша организация обладает максимальной защитой, настройка и развертывание решения безопасности с помощью процесса, который включает следующие действия:

1. [Настройка многофакторной проверки подлинности и политики условного доступа](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Настройка Microsoft Defender для удостоверений](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Включение Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Настройка Defender для Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Настройка Microsoft Defender для конечной точки](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Настройка безопасности облачных приложений Майкрософт](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Мониторинг состояния и действия](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Обучение пользователей](deploy-threat-protection-configure.md#step-8-train-users)

Функции защиты от угроз можно настраивать параллельно, поэтому если у вас есть несколько групп сетевой безопасности, отвечающих за различные службы, они могут настроить функции защиты организации одновременно.

## <a name="next-step"></a>Следующий шаг


![Процесс развертывания возможностей защиты от угроз](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Настройка [возможностей защиты от угроз в Microsoft 365](deploy-threat-protection-configure.md)

