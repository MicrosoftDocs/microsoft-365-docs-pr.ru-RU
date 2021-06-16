---
title: Переключение с защиты конечных точек, не в microsoft, на Microsoft Defender для конечной точки
description: Переключение на Microsoft Defender для конечной точки. Ознакомьтесь с этой статьей для обзора.
keywords: миграция, расширенные средства защиты конечной точки защитника Windows для Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365solution-migratetomdatp
- m365solution-overview
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2953103cb3812103740f98a6db5b8f4d369731e3
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930311"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Переключение с защиты конечных точек, не в microsoft, на Microsoft Defender для конечной точки

Если вы думаете о переходе из решения защиты конечной точки, не от Microsoft, в Microsoft Defender для конечной точки (Defender for [Endpoint),](microsoft-defender-endpoint.md) вы находитесь в правильном месте. Используйте эту статью в качестве руководства.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Обзор миграции в Defender для конечной точки":::

При переходе на Defender для конечной точки вы начинаете с решения, не входить в Microsoft, работая в активном режиме. Затем настраивайте Defender для конечной точки в пассивном режиме и на борту устройств в Defender для конечной точки. Далее вы установите Защитник для конечной точки в активный режим. Наконец, вы удалите решение, не в microsoft.

## <a name="the-migration-process"></a>Процесс миграции

Процесс миграции в Defender для конечной точки можно разделить на три этапа, как описано в следующей таблице:

![Этапы миграции — подготовка, настройка, бортовой](images/phase-diagrams/migration-phases.png)

|Этап |Описание |
|--|--|
|[Подготовка к миграции](switch-to-microsoft-defender-prepare.md) |На [ **этапе Подготовка:**](switch-to-microsoft-defender-prepare.md) <p>1. Обновление устройств организации. <p>2. Получить Defender для конечной точки. <p>3. Планирование ролей и разрешений и предоставление доступа к Центр безопасности в Microsoft Defender. <p>4. Настройте прокси-сервер устройства и параметры Интернета, чтобы включить связь между устройствами организации и Защитником для конечной точки. |
|[Настройка Защитника для конечной точки](switch-to-microsoft-defender-setup.md) |На [ **этапе установки:**](switch-to-microsoft-defender-setup.md) <p>1. Включить/переустановить антивирусная программа в Microsoft Defender. <p>2. Настройка защитника для конечной точки. <p>3. Добавьте Защитник для конечной точки в список исключений для существующего решения. <p>4. Добавьте существующее решение в список исключений для антивирусная программа в Microsoft Defender. <p>5. Настройка групп устройств, коллекций и организационных подразделений. <p>6. Настройка политик антивирусного обеспечения и параметров защиты в режиме реального времени.|
|[Onboard to Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |На [ **этапе onboard:**](switch-to-microsoft-defender-onboard.md) <p>1. На борту устройств в Defender для конечной точки. <p>2. Выполнить тест обнаружения. <p>3. Подтверждение того, что антивирусная программа в Microsoft Defender работает в пассивном режиме. <p>4. Получить обновления для антивирусная программа в Microsoft Defender. <p>5. Удалить существующее решение защиты конечной точки. <p>6. Убедитесь, что Defender для конечной точки работает правильно. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Что включено в Microsoft Defender для конечной точки?

В этом руководстве по [](microsoft-defender-antivirus-in-windows-10.md) миграции мы уделяем основное внимание защите и [возможностям](overview-endpoint-detection-response.md) обнаружение и нейтрализация атак на конечные точки следующего поколения в качестве отправной точки для перехода в Defender для конечной точки. Тем не менее, Defender for Endpoint включает в себя гораздо больше, чем антивирусная и конечная точки защиты. Defender for Endpoint — это единая платформа для профилактической защиты, обнаружения нарушений, автоматического расследования и реагирования. В следующей таблице обобщены функции и возможности в Defender for Endpoint. 

| Feature/Capability | Описание |
|---|---|
| [Управление контролем угроз и уязвимостями](next-gen-threat-and-vuln-mgt.md) | Возможности & управление уязвимостями помогают выявлять, оценивать и устранять недостатки в конечных точках (например, устройствах). |
| [Сокращение направлений атак](overview-attack-surface-reduction.md) | Правила уменьшения поверхности атаки помогают защитить устройства и приложения организации от киберугроз и атак. |
| [Защита нового поколения](microsoft-defender-antivirus-in-windows-10.md) | Защита следующего поколения включает в себя антивирусная программа в Microsoft Defender для блокировки угроз и вредоносных программ. |
| [Обнаружение и устранение угроз на конечных точках](overview-endpoint-detection-response.md) | Возможности обнаружения и реагирования конечной точки обнаруживают, исследуют и реагируют на попытки вторжения и активные нарушения.  |
| [Расширенная охота](advanced-hunting-overview.md) | Расширенные возможности охоты позволяют группе операций безопасности находить индикаторы и объекты известных или потенциальных угроз. |
| [Блокировка с учетом поведения и автономность](behavioral-blocking-containment.md) | Возможности поведенческой блокировки и сдерживания помогают выявлять и останавливать угрозы, основываясь на их поведении и деревьях обработки даже при выполнении угрозы. |
| [Автоматическое расследование и исправление](automated-investigations.md) | Возможности автоматического расследования и реагирования проверяют оповещения и принимают незамедлительных действий по устранению нарушений. |
| [Служба охоты на](microsoft-threat-experts.md) угрозы (эксперты Майкрософт по угрозам) | Службы охоты на угрозы предоставляют группам операций безопасности мониторинг и анализ на уровне экспертов, а также для обеспечения того, чтобы критические угрозы не были пропущены. |

**Хотите узнать больше? См. [в "Защитнике для конечной точки".](microsoft-defender-endpoint.md)**

## <a name="next-step"></a>Следующий этап

- Приступить к [подготовке к миграции](switch-to-microsoft-defender-prepare.md).
