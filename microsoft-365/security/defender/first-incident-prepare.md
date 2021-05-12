---
title: Подготовка позиции безопасности к первому инциденту
description: Настройка позы безопасности Microsoft 365 клиента для первого инцидента в Microsoft 365 Defender.
keywords: инциденты, оповещения, исследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверение, почтовый ящик, электронная почта, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 76bead8fd855e4119db6297d2ab1a3d08d64a48c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297168"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>Подготовка позиции безопасности к первому инциденту

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

Подготовка к обработке инцидентов включает создание достаточной защиты сети организации от различных типов инцидентов безопасности. Чтобы снизить риск инцидентов с безопасностью, Национальный институт стандартов и технологий (NIST) рекомендует несколько методов безопасности, включая оценку рисков, ужесточить безопасность хостов, безопасно настраивать сети и предотвращать вредоносные программы. 

Microsoft 365 Defender может помочь в решении нескольких аспектов предотвращения инцидентов: 

- Реализация [нулевой структуры доверия](https://docs.microsoft.com/security/zero-trust/)
- Определение позиции безопасности, назначив оценку с [помощью Microsoft Secure Score](microsoft-secure-score.md)
- Предотвращение угроз с помощью оценок уязвимости в [управлении угрозами и уязвимостью](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Понимание последних угроз безопасности, чтобы вы могли подготовиться к ним

## <a name="step-1-implement-zero-trust"></a>Этап 1. Реализация нулевого доверия

[Zero Trust](https://docs.microsoft.com/security/zero-trust/) — это интегрированная философия безопасности и целостная стратегия, учитывая сложный характер любой современной среды, включая рабочую силу мобильных устройств и пользователей, устройства, приложения и данные, где бы они ни находились. Предоставляя единую стеклянную области для согласованного управления всеми обнаружениями конечных точек, Microsoft 365 Defender может упростить для [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) вашей группы операций безопасности реализацию руководящих принципов Zero Trust. 

Компоненты Microsoft 365 Defender могут отображать нарушения правил, которые были реализованы для создания политик условного доступа для Zero Trust путем интеграции данных из Microsoft Defender для конечной точки (MDE) или других поставщиков мобильной безопасности в качестве источника информации для политик соответствия требованиям устройств и реализации политик условного доступа на основе устройств. 

Риск устройства напрямую влияет на то, какие ресурсы будут доступны пользователю этого устройства. Отказ в доступе к ресурсам на основе определенных критериев является основной темой Zero Trust и Microsoft 365 Defender предоставляет сведения, необходимые для определения критериев уровня доверия. Например, Microsoft 365 Defender может предоставлять уровень версии программного обеспечения устройства через страницу Управления угрозами и уязвимостью, а политики условного доступа ограничивают устройства с устаревшими или уязвимыми версиями.

Автоматизация является важной частью реализации и поддержания среды нулевого доверия, а также сокращения количества оповещений, которые потенциально могут привести к событиям реагирования на инциденты. Компоненты Microsoft 365 Defender можно автоматизировать, такие [](m365d-autoir.md) как действия по исправлению (известные как расследования инцидента в центре безопасности Microsoft 365), действия уведомления и даже создание билетов поддержки, таких как [ServiceNow](https://microsoft.service-now.com/sp/).

## <a name="step-2-determine-your-organizations-security-posture"></a>Этап 2. Определение позиции безопасности организации

Далее организации могут использовать microsoft [Secure Score](microsoft-secure-score.md) в Microsoft 365 Defender, чтобы определить текущую позицию безопасности и рассмотреть рекомендации по ее улучшению. Чем выше оценка, тем больше рекомендаций по безопасности и действий по улучшению было принято организацией. Рекомендации по безопасной оценке можно использовать для различных продуктов и позволяют организациям повышать свои оценки еще выше. 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Пример показателей безопасности Майкрософт в центре безопасности Майкрософт":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>Этап 3. Оценка уязвимости организации

Предотвращение инцидентов может помочь оптимизировать усилия по обеспечению безопасности, чтобы сосредоточиться на критически важных и важных инцидентах безопасности. Уязвимости программного обеспечения часто являются предотвратимой точкой входа для атак, которые могут привести к краже данных, потере данных или нарушению бизнес-операций. Если не происходит никаких атак, операции безопасности должны стремиться к достижению и поддержанию приемлемого уровня уязвимости [в](../defender-endpoint/tvm-exposure-score.md) своей организации.

Чтобы проверить ход исправления программного [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) обеспечения, посетите страницу Управления угрозами и уязвимостью в Defender for Endpoint, к которой можно получить доступ из Microsoft 365 Defender через вкладку **More resources.**

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Пример страницы &quot;Угроза и уязвимость&quot; в центре безопасности Майкрософт"::: 
 
## <a name="4-understand-emerging-threats"></a>4. Понимание возникающих угроз

Используйте [аналитику угроз](threat-analytics.md) в центре Microsoft 365 безопасности, чтобы быть в курсе текущего ландшафта угроз безопасности. Специалисты по безопасности Майкрософт создают отчеты, в них подробно описываются последние киберугрозы, чтобы вы могли понять, как они могут повлиять на Microsoft 365 подписку, устройства и пользователей. Эти отчеты могут включать:

- Активные субъекты угроз и их кампании
- Популярные и новые методы атаки
- Критические уязвимости
- Общие поверхности атаки
- Распространенные вредоносные программы

Вы можете реализовать рекомендации появляющейся угрозы, чтобы укрепить осанку безопасности и свести к минимуму область поверхности атаки.

Уделайте время в расписании, чтобы регулярно проверять раздел [Threat Analytics](threat-analytics.md) центра Microsoft 365 безопасности.

## <a name="next-step"></a>Следующий шаг

[![Шаг 1. Узнайте, как анализировать и анализировать инциденты](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)

Узнайте, как анализировать и анализировать [инциденты.](first-incident-analyze.md)

## <a name="see-also"></a>См. также

- [Обзор инцидентов](incidents-overview.md)
- [Исследование инцидентов](investigate-incidents.md)
- [Управление инцидентами](manage-incidents.md)