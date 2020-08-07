---
title: Развертывание возможностей защиты от угроз в Microsoft 365
description: Узнайте, как развертывать службы и возможности защиты от угроз в Microsoft 365.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 312df25bf4fe2b91bb60b4122378b4457b25723c
ms.sourcegitcommit: b812771805c8b9e92b64deb1928e265e60d80405
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588188"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Развертывание возможностей защиты от угроз в Microsoft 365

[Вредоносные программы](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)и сложные кибератаки, такие как [угрозы без файлов](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), являются распространенным событием. Предприятиям необходимо защищать себя и их клиентов. Атаки безопасности кибератак могут привести к серьезным проблемам в Организации, от потери доверия до финансовых воес, простоев бизнес-угрожающие материалы и т. д. Защита от угроз имеет важное значение, но может быть трудно определить, где следует уделить время, усилия и ресурсы Организации. 

Решения для обеспечения безопасности Майкрософт встроены в наши продукты и службы. Возможности автоматизации и машинного обучения снижают нагрузку на группы по обеспечению безопасности, чтобы убедиться в том, что нужные элементы направлены. А надежность решений Майкрософт по обеспечению безопасности основаны на триллионсх, которые обрабатываются ежедневно в нашем [интеллектуальном графе безопасности](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph). Решения Microsoft 365 для обеспечения безопасности включают в себя [защиту от угроз Майкрософт](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), которая объединяет сигналы электронной почты, данных, устройств и удостоверений, чтобы прокрасить изображение сложных угроз для Организации.

В этом видеоролике приводится обзор процесса развертывания.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Используйте эту статью в качестве руководства по внедрению решения для защиты от угроз.

## <a name="threat-protection-in-microsoft-365-e5"></a>Защита от угроз в Microsoft 365

[Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) , что позволяет защищать организацию с помощью адаптивной встроенной аналитики. С помощью функций защиты от угроз в Microsoft 365, вы можете обнаружить и исследовать расширенные угрозы, скомпрометированные удостоверения и вредоносные действия в локальной и облачной среде.

В Microsoft 365 е функции защиты от угроз интегрированы по умолчанию. Подается сигнал от каждой возможности — возможность обнаруживать угрозы и реагировать на них. Комбинированный набор возможностей обеспечивает наилучшую защиту для организаций, особенно многоязычных организаций, по сравнению с выполнением продуктов, не относящихся к корпорации Майкрософт. На следующем рисунке изображены службы и функции защиты от угроз в Microsoft 365, описанные в этой статье.

![Обзор защиты от угроз Майкрософт](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Как только вы развертываете какие — расширенные возможности защиты от угроз, вы можете включить защиту от угроз Майкрософт, которая переводит сигналы и данные в одном месте. 

![Концептуальная иллюстрация панели мониторинга Microsoft Threat protection](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

На следующем рисунке представлен рекомендуемый путь для развертывания отдельных возможностей. 

![Сигналы защиты от угроз M365](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Решение и возможности  |Описание  |
|---------|---------|
|Многофакторная проверка подлинности и условный доступ     |Защита от скомпрометированных удостоверений и устройств. Начните с этой защиты, так как это основано. Конфигурация, рекомендуемая в этом руководстве, включает в себя защиту удостоверения Azure AD.     |
|Расширенная защита от угроз Azure     |  Облачное решение для обеспечения безопасности, использующее локальные сигналы Active Directory для определения, обнаружения и исследования сложных угроз, скомпрометированных удостоверений и действий по предварительной программе предварительной оценки, направленных в организацию. Обратите внимание на службу Advanced Threat Protection в Azure, так как она защищает локальную среду и облачную инфраструктуру, не имеет зависимостей и предварительных требований, а также может обеспечить немедленную пользу.       | 
|Office 365 Advanced Threat Protection     | Защищает организацию от вредоносных угроз, исносящихся к сообщениям электронной почты, ссылкам (URL-адресам) и средствам совместной работы. Защита от вредоносных программ, фишинговых атак, подмены и других типов атак. Настройка Office 365 Advanced Threat protection рекомендуется выполнять следующим путем, так как управление изменениями, перенос параметров из системы инкумбент и другие соображения могут занимать больше длительного развертывания. <br><br>Примечание: необходимо настроить возможности защиты от угроз, включенные во все подписки на Office 365 (Exchange Online Protection).       |
|Advanced Threat Protection в Microsoft Defender    | Платформа Endpoint Protection, которая помогает предотвращать, обнаруживать и отвечать на расширенные угрозы. Для развертывания Advanced Threat Protection в защитнике Майкрософт может потребоваться некоторое время, но настройка может выполняться параллельно с другими возможностями.   |
|Microsoft Cloud App Security     |   Брокер безопасности облачного доступа для обнаружения, исследования и управления. Вы можете включить Microsoft Cloud App Security, прежде чем приступать к сбору данных и аналитических данных. Реализация информации и другой целевой защиты в приложениях SaaS включает планирование и может занять больше времени.       | 

> [!TIP]
> Организации с несколькими участниками группы безопасности могут параллельно реализовать эти возможности.

## <a name="deploy-your-threat-protection-solution"></a>Развертывание решения для защиты от угроз

Чтобы убедиться в том, что ваша организация обладает лучшей защитой, установите и разверните свое решение по обеспечению безопасности, чтобы включить следующие действия:

1. [Настройка многофакторной проверки подлинности и политик условного доступа](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Настройка Advanced Threat Protection в Azure](deploy-threat-protection-configure.md#step-2-configure-azure-advanced-threat-protection)
3. [Включение Защиты от угроз (Майкрософт)](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-threat-protection)
4. [Настройка Office 365 Advanced Threat protection](deploy-threat-protection-configure.md#step-4-configure-office-365-advanced-threat-protection)
5. [Настройка Advanced Threat Protection в защитнике Майкрософт](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [Настройка Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Отслеживание состояния и выполнение действий](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Обучение пользователей](deploy-threat-protection-configure.md#step-8-train-users)

Функции защиты от угроз можно настроить параллельно, поэтому при наличии нескольких групп безопасности, ответственных за различные службы, они могут настраивать функции защиты Организации одновременно. На следующей схеме показан процесс высокого уровня для развертывания возможностей защиты от угроз. 

![Процесс развертывания средств защиты от угроз](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 


