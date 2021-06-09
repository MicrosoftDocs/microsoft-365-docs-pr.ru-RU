---
title: Перенос из Symantec в Microsoft Defender для конечной точки
description: Сведения о том, как перейти из Symantec в Microsoft Defender для конечной точки
keywords: миграция, Microsoft Defender для конечной точки, edr
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
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 62a916fcf89432a512ada1b85002cce401e4dd23
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530902"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>Перенос из Symantec в Microsoft Defender для конечной точки
Если вы планируете перейти с Symantec Endpoint Protection (Symantec) на [Microsoft Defender для](microsoft-defender-endpoint.md) конечной точки (Microsoft Defender для конечной точки), вы находитесь в правильном месте. Используйте эту статью в качестве руководства.

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="Обзор переноса из Symantec в Defender для конечной точки":::

При переходе от Symantec к Defender для endpoint вы начинаете с решения Symantec в активном режиме, настраиваете Defender для конечной точки в пассивном режиме, на борту в Defender для конечной точки, а затем установите Defender for Endpoint в активный режим и удалите Symantec.

## <a name="the-migration-process"></a>Процесс миграции

При переходе из Symantec в Microsoft Defender для конечной точки следует процесс, который можно разделить на три этапа, как описано в следующей таблице:

![Этапы миграции — подготовка, настройка, бортовой](images/phase-diagrams/migration-phases.png)

|Этап |Описание |
|--|--|
|[Подготовка к миграции](symantec-to-microsoft-defender-atp-prepare.md) |На **этапе Подготовки** вы обновляете устройства организации, получаете Microsoft Defender для конечной точки, планируете роли и разрешения и предоставляете доступ к Центр безопасности в Microsoft Defender. Вы также настраивает прокси-сервер устройства и параметры Интернета, чтобы включить связь между устройствами организации и Защитником для конечной точки. |
|[Настройка Microsoft Defender для конечной точки](symantec-to-microsoft-defender-atp-setup.md) |На **этапе установки** вы включаете антивирусная программа в Microsoft Defender и установите его в пассивный режим. Также настраиваются параметры & исключений для антивирусная программа в Microsoft Defender и Symantec Endpoint Protection. Затем создайте группы устройств, коллекции и организационные подразделения. Наконец, настраиваются политики защиты от антивирусных программ и параметры защиты в режиме реального времени.|
|[Onboard to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-onboard.md) |На этапе **onboard** вы на борту устройств в Microsoft Defender для конечной точки убедитесь, что антивирус защитника Microsfot запущен в пассивном режиме, и убедитесь, что конечные точки общаются с Defender для конечной точки. Затем удалить Symantec и убедиться, что Defender для конечной точки работает правильно. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Что включено в Microsoft Defender для конечной точки?

В этом руководстве по [](microsoft-defender-antivirus-in-windows-10.md) миграции мы уделяем основное внимание защите и [возможностям](overview-endpoint-detection-response.md) обнаружение и нейтрализация атак на конечные точки следующего поколения в качестве отправной точки для перехода в Microsoft Defender для endpoint. Тем не менее, Microsoft Defender для конечной точки включает в себя гораздо больше, чем антивирусная и конечная точка защиты. Microsoft Defender для конечной точки — это унифицированная платформа безопасности для конечных точек, которая обеспечивает превентивную защиту, обнаружение после взлома, автоматическое исследования и реагирование. В следующей таблице обобщены функции и возможности в Microsoft Defender для конечной точки. 

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

**Хотите узнать больше? См. [в веб-сайте Microsoft Defender для конечной точки](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Следующий этап

- Приступить к [подготовке к миграции](symantec-to-microsoft-defender-atp-prepare.md).
