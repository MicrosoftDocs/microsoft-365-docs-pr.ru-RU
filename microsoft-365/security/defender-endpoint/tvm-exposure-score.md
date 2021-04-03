---
title: Оценка экспозиции в управлении угрозами и уязвимостью
description: Оценка воздействия на управление рисками и уязвимостями отражает уязвимость организации к угрозам кибербезопасности.
keywords: оценка экспозиции, оценка экспозиции mdatp, оценка экспозиции mdatp tvm, оценка экспозиции организации, оценка экспозиции организации tvm, управление угрозами и уязвимостью, Microsoft Defender для Endpoint
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34c3122b017b14605fdbb3358f31f73e26361a4d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500127"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a>Оценка экспозиции — управление угрозами и уязвимостью

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Управление угрозами и уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Оценка экспозиции отображается на [панели](tvm-dashboard-insights.md) управления угрозами и уязвимостью Центра безопасности Microsoft Defender. Это отражает уязвимость организации к угрозам кибербезопасности. Низкая оценка экспозиции означает, что ваши устройства менее уязвимы от эксплуатации.

- Быстрое понимание и определение высокоуровневой информации о состоянии безопасности в вашей организации.
- Обнаружение и реагирование на области, которые требуют расследования или действий для улучшения текущего состояния.
- Общение с коллегами и руководством о влиянии усилий по обеспечению безопасности.

Карта позволяет просматривать тенденцию оценки экспозиции на высоком уровне со временем. Любые всплески в диаграмме дают наглядное представление о высокой угрозе кибербезопасности, которую можно исследовать далее.

![Карта показателей экспозиции](images/tvm_exp_score.png)

## <a name="how-it-works"></a>Принципы работы

Оценка экспозиции разбита на следующие уровни:

- 0-29: низкая оценка экспозиции
- 30-69: средняя оценка экспозиции
- 70-100: высокая оценка экспозиции

Вы можете устранять проблемы, основываясь [](tvm-security-recommendation.md) на рекомендациях по безопасности с приоритетами, чтобы снизить оценку экспозиции. У каждого программного обеспечения есть недостатки, которые преобразуются в рекомендации и приоритизируются в зависимости от риска для организации.

## <a name="reduce-your-threat-and-vulnerability-exposure"></a>Уменьшение воздействия угроз и уязвимостей

Снижение воздействия угрозы и уязвимости путем устранения [рекомендаций по безопасности.](tvm-security-recommendation.md) Сделайте наибольшее влияние на оценку экспозиции, изменив верхние рекомендации по безопасности, которые можно просмотреть в панели управления угрозами и [уязвимостями.](tvm-dashboard-insights.md)

## <a name="related-topics"></a>Статьи по теме

- [Обзор управления угрозами и уязвимостью](next-gen-threat-and-vuln-mgt.md)
- [Оценка безопасности (Майкрософт) для устройств](tvm-microsoft-secure-score-devices.md)
- [Рекомендации по безопасности](tvm-security-recommendation.md)
- [Временная шкала события](threat-and-vuln-mgt-event-timeline.md)
