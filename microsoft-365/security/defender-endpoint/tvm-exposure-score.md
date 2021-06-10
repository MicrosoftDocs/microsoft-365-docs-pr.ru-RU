---
title: Оценка экспозиции в контроль угроз и уязвимостей
description: Оценка контроль угроз и уязвимостей отображает, насколько ваша организация уязвима для угроз кибербезопасности.
keywords: оценка экспозиции, оценка экспозиции Microsoft Defender для конечной точки, оценка экспозиции Microsoft Defender для endpoint tvm, оценка экспозиции организации, оценка экспозиции организации tvm, контроль угроз и уязвимостей, Microsoft Defender для Endpoint
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
ms.openlocfilehash: fcea240fe1dc0ce97a2800391320b04c39c84336
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934109"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a>Оценка экспозиции — контроль угроз и уязвимостей

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Угроза и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Оценка экспозиции отображается в панели управление уязвимостями и [Центр безопасности в Microsoft Defender.](tvm-dashboard-insights.md) Это отражает уязвимость организации к угрозам кибербезопасности. Низкая оценка экспозиции означает, что ваши устройства менее уязвимы от эксплуатации.

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

Снижение воздействия угрозы и уязвимости путем устранения [рекомендаций по безопасности.](tvm-security-recommendation.md) Сделайте наибольшее влияние на оценку экспозиции, изменив верхние рекомендации по [безопасности,](tvm-dashboard-insights.md)которые можно просмотреть на панели мониторинга контроль угроз и уязвимостей.

## <a name="related-topics"></a>Статьи по теме

- [Обзор угроз и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Оценка безопасности (Майкрософт) для устройств](tvm-microsoft-secure-score-devices.md)
- [Рекомендации по безопасности](tvm-security-recommendation.md)
- [Временная шкала события](threat-and-vuln-mgt-event-timeline.md)
