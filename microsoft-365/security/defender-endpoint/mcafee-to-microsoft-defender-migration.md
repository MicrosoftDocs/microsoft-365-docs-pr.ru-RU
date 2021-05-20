---
title: Миграция из McAfee в Microsoft Defender для конечной точки
description: Переключение с McAfee на Microsoft Defender для конечной точки. Ознакомьтесь с этой статьей для обзора.
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
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 5bbcf885ec160204916507aee60398aee35e470b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538055"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>Миграция из McAfee в Microsoft Defender для конечной точки

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Если вы планируете перейти из McAfee Endpoint Security (McAfee) в [Microsoft Defender для](microsoft-defender-endpoint.md) конечной точки (Microsoft Defender для конечной точки), вы находитесь в правильном месте. Используйте эту статью в качестве руководства.


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="Обзор миграции из McAfee в Defender для конечной точки":::

При переходе из McAfee в Defender для конечной точки вы начинаете с решения McAfee в активном режиме, настраиваете Defender для конечной точки в пассивном режиме, на борту в Defender для конечной точки, а затем установите Defender for Endpoint в активный режим и удалите McAfee.

## <a name="the-migration-process"></a>Процесс миграции

При переходе из McAfee в Microsoft Defender для конечной точки следует процесс, который можно разделить на три этапа: подготовка, настройка и борт. 

![Этапы миграции — подготовка установки на борту](images/phase-diagrams/migration-phases.png)

|Этап |Описание |
|--|--|
|[Подготовка к миграции](mcafee-to-microsoft-defender-prepare.md) |На [**этапе Подготовки**](mcafee-to-microsoft-defender-prepare.md) вы обновляете устройства организации, получаете Microsoft Defender для конечной точки, планируете роли и разрешения и предоставляете доступ к Центр безопасности в Microsoft Defender. Вы также настройте прокси-сервер устройства и параметры Интернета, чтобы включить связь между устройствами организации и Microsoft Defender для конечной точки. |
|[Настройка Microsoft Defender для конечной точки](mcafee-to-microsoft-defender-setup.md) |На [**этапе установки**](mcafee-to-microsoft-defender-setup.md) вы включаете антивирусная программа в Microsoft Defender и установите его в пассивный режим. Также настраиваются параметры & исключений для антивирусная программа в Microsoft Defender и существующего решения по защите конечной точки. Затем создайте группы устройств, коллекции и организационные подразделения. Наконец, настраиваются политики защиты от антивирусных программ и параметры защиты в режиме реального времени.|
|[Onboard to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-onboard.md) |На этапе [**onboard**](mcafee-to-microsoft-defender-onboard.md) вы на борту устройств в Microsoft Defender для конечной точки убедитесь, что антивирусная программа в Microsoft Defender работает в пассивном режиме, и убедитесь, что конечные точки общаются с Защитником для конечной точки. Затем необходимо удалить McAfee и убедиться, что Defender for Endpoint работает правильно. |

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

## <a name="next-step"></a>Следующий шаг

- Приступить к [подготовке к миграции](mcafee-to-microsoft-defender-prepare.md).
