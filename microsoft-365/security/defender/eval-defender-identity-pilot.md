---
title: Пилот microsoft Defender for Identity, настройка контрольных показателей конфигурации, стандартов, рекомендаций и руководство по обнаружению и исправлению различных угроз удостоверений, таких как разведка, скомпрометированная учетная запись, поодальное перемещение, доминирование домена и оповещений об эксфильтрации, проведение исследования путей пользовательского, компьютерного, юридического и более позднего движения.
description: Пилот Microsoft Defender for Identity, задайте ориентиры, сдайте учебники по разведке, скомпрометированию учетных данных, дальнейшему движению, доминированию домена и оповещениям об эксфильтрации.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458550"
---
# <a name="pilot-microsoft-defender-for-identity"></a>Пилотный защитник Майкрософт для удостоверений


**Область применения:**
- Microsoft 365 Defender

Эта статья — [шаг 3 из 3](eval-defender-identity-overview.md) в процессе настройки среды оценки для Microsoft Defender для identity. Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-identity-overview.md)

Чтобы настроить пилотный пилот для Microsoft Defender для удостоверений, используйте следующие действия. Обратите внимание, что рекомендации не включают настройку пилотной группы. Передовой практикой является установка датчика на всех серверах с службами домена Active Directory (AD DS) и Active Directory Federated Services (AD FS).

![Действия по добавлению защитника Microsoft Defender для удостоверений в среду оценки Defender](../../media/defender/m365-defender-identity-pilot-steps.png)

В следующей таблице описываются действия на иллюстрации.

- [Шаг 1. Настройка базовых рекомендаций для среды удостоверений](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [Шаг 2. Опробуйте возможности — пройдитесь по учебникам по выявлению и исправлению различных типов атак ](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a>Этап 1. Настройка базовых рекомендаций для среды удостоверений

Корпорация Майкрософт предоставляет базовые рекомендации по безопасности для клиентов, использующих облачные службы Майкрософт. Эталон [безопасности Azure (ASB)](/security/benchmark/azure/overview) содержит рекомендации и рекомендации, которые помогут повысить безопасность рабочих нагрузок, данных и служб в Azure.

Эти базовые рекомендации включают [базовую базу безопасности Azure для Microsoft Defender for Identity.](/security/benchmark/azure/baselines/defender-for-identity-security-baseline) Реализация этих рекомендаций может занять некоторое время для планирования и реализации. Хотя это значительно повышает безопасность среды удостоверений, они не должны препятствовать продолжению оценки и реализации Microsoft Defender for Identity. Эти данные предоставляются здесь для вашего информирования.

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a>Этап 2. Опробуйте возможности — пройдитесь по учебникам по выявлению и исправлению различных типов атак

Документация По защитнику удостоверений Майкрософт включает ряд учебных пособий, которые проходят процесс выявления и устранения различных типов атак.

Опробуйте учебники Defender для identity:
- [Оповещений о разведке](/defender-for-identity/reconnaissance-alerts)
- [Скомпрометированная оповещение учетных данных](/defender-for-identity/compromised-credentials-alerts)
- [Оповещений о дальнейшем движении](/defender-for-identity/lateral-movement-alerts)
- [Оповещений о доминировании домена](/defender-for-identity/domain-dominance-alerts)
- [Оповещений exfiltration](/defender-for-identity/exfiltration-alerts)
- [Исследование пользователя](/defender-for-identity/investigate-a-user)
- [Исследование компьютера](/defender-for-identity/investigate-a-computer)
- [Изучение путей движения на более поздних путях](/defender-for-identity/investigate-lateral-movement-path)
- [Исследование сущностями](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a>Дальнейшие действия

[Оценка Microsoft Defender для Office 365](eval-defender-office-365-overview.md)

Вернись к обзору [для Оценки Microsoft Defender для Office 365](eval-defender-office-365-overview.md)

Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)