---
title: Перенос из Symantec в Microsoft Defender для конечной точки
description: Сведения о том, как перейти из Symantec в Microsoft Defender для конечной точки
keywords: миграция, защита от угроз защитника Windows, atp, edr
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
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 6517359c805bb449d075e401283a79a791461630
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218804"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>Перенос из Symantec в Microsoft Defender для конечной точки
Если вы планируете перейти с Symantec Endpoint Protection (Symantec) на [Microsoft Defender для](https://docs.microsoft.com/windows/security/threat-protection) конечной точки (Microsoft Defender для конечной точки), вы находитесь в правильном месте. Используйте эту статью в качестве руководства.

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
|[Подготовка к миграции](symantec-to-microsoft-defender-atp-prepare.md) |На **этапе Подготовки** вы получите Microsoft Defender для конечной точки, спланируйте роли и разрешения и получите доступ к Центру безопасности Защитника Майкрософт. Вы также настройте прокси-сервер устройства и параметры Интернета, чтобы включить связь между устройствами организации и Microsoft Defender для конечной точки. |
|[Настройка Microsoft Defender для конечной точки](symantec-to-microsoft-defender-atp-setup.md) |На **этапе установки** настраиваются параметры и исключения для антивируса Microsoft Defender, Microsoft Defender для конечной точки и защиты конечных точек Symantec. Вы также создаете группы устройств, коллекции и организационные подразделения. Наконец, настраиваются политики защиты от антивирусных программ и параметры защиты в режиме реального времени.|
|[Onboard to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-onboard.md) |На **этапе onboard** вы на борту устройств в Microsoft Defender для конечной точки и убедитесь, что эти устройства общаются с Microsoft Defender для конечной точки. Наконец, необходимо удалить Symantec и убедиться, что защита через Microsoft Defender для конечной точки находится в активном режиме. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Что включено в Microsoft Defender для конечной точки?

В этом руководстве по [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) миграции основное внимание уделяется возможностям обнаружения и реагирования конечных точек следующего поколения в качестве отправной точки для перехода в Microsoft Defender для конечной точки. [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) Тем не менее, Microsoft Defender для конечной точки включает в себя гораздо больше, чем антивирусная и конечная точка защиты. Microsoft Defender для конечной точки — это унифицированная платформа безопасности для конечных точек, которая обеспечивает превентивную защиту, обнаружение после взлома, автоматическое исследования и реагирование. В следующей таблице обобщены функции и возможности в Microsoft Defender для конечной точки. 

| Feature/Capability | Описание |
|---|---|
| [Управление & уязвимостей](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Возможности управления & уязвимостей помогают выявлять, оценивать и устранять недостатки в конечных точках (например, устройствах). |
| [Сокращение направлений атак](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | Правила уменьшения поверхности атаки помогают защитить устройства и приложения организации от киберугроз и атак. |
| [Защита следующего поколения](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | Защита следующего поколения включает антивирус Microsoft Defender, который помогает блокировать угрозы и вредоносные программы. |
| [Обнаружение и устранение угроз на конечных точках](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | Возможности обнаружения и реагирования конечной точки обнаруживают, исследуют и реагируют на попытки вторжения и активные нарушения.  |
| [Расширенная охота на угрозы](advanced-hunting-overview.md) | Расширенные возможности охоты позволяют группе операций безопасности находить индикаторы и объекты известных или потенциальных угроз. |
| [Блокировка и сдерживание поведения](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | Возможности поведенческой блокировки и сдерживания помогают выявлять и останавливать угрозы, основываясь на их поведении и деревьях обработки даже при выполнении угрозы. |
| [Автоматическое исследование и защита](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | Возможности автоматического расследования и реагирования проверяют оповещения и принимают незамедлительных действий по устранению нарушений. |
| [Служба охоты на угрозы](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Эксперты по угрозам Майкрософт) | Службы охоты на угрозы предоставляют группам операций безопасности мониторинг и анализ на уровне экспертов, а также для обеспечения того, чтобы критические угрозы не были пропущены. |

**Хотите узнать больше? См. [в веб-сайте Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection).**

## <a name="next-step"></a>Следующий шаг

- Приступить к [подготовке к миграции](symantec-to-microsoft-defender-atp-prepare.md).
