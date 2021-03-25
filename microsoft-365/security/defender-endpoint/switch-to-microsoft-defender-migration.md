---
title: Переключение из решения конечной точки, не в microsoft, в Microsoft Defender для конечной точки
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
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 02/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 6e5b79e447579631e4aa2eaf02352dc3fa6a8daa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074126"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Переключение из решения конечной точки, не в microsoft, в Microsoft Defender для конечной точки

Если вы планируете перейти из решения защиты конечной точки, не от Microsoft, в Microsoft Defender для конечной точки (Defender for [Endpoint),](https://docs.microsoft.com/windows/security/threat-protection) вы находитесь в правильном месте. Используйте эту статью в качестве руководства.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Обзор миграции в Defender для конечной точки":::

При переходе на Защитник для конечной точки вы начинаете с решения, не входить в Microsoft, в активном режиме, настраиваете Defender для конечной точки в пассивном режиме, на борту в Defender для конечной точки, а затем установите Defender for Endpoint в активный режим и удалите решение, не включаемое в Microsoft.

> [!TIP]
> - Если вы в настоящее время используете безопасность конечных точек McAfee (McAfee), см. в этой записи миграция из [McAfee в Microsoft Defender для конечной точки.](mcafee-to-microsoft-defender-migration.md)
> - Если вы в настоящее время используете Symantec Endpoint Protection (Symantec), см. в записи Миграция из [Symantec в Microsoft Defender для конечной точки.](symantec-to-microsoft-defender-atp-migration.md)

## <a name="the-migration-process"></a>Процесс миграции

При переходе в Microsoft Defender для конечной точки следует процесс, который можно разделить на три этапа, как описано в следующей таблице:

![Этапы миграции — подготовка, настройка, бортовой](images/phase-diagrams/migration-phases.png)

|Этап |Описание |
|--|--|
|[Подготовка к миграции](switch-to-microsoft-defender-prepare.md) |На [ **этапе Подготовка**](switch-to-microsoft-defender-prepare.md)вы обновляете устройства организации, получаете Microsoft Defender для конечной точки, планируете роли и разрешения и предоставляете доступ к Центру безопасности Microsoft Defender. Вы также настройте прокси-сервер устройства и параметры Интернета, чтобы включить связь между устройствами организации и Microsoft Defender для конечной точки. |
|[Настройка Microsoft Defender для конечной точки](switch-to-microsoft-defender-setup.md) |На [  ](switch-to-microsoft-defender-setup.md)этапе установки вы включаете антивирус Microsoft Defender и убедитесь, что он в пассивном режиме, и настраивайте параметры & для антивируса Microsoft Defender, Microsoft Defender для конечной точки и существующего решения по защите конечной точки. Вы также создаете группы устройств, коллекции и организационные подразделения. Наконец, настраиваются политики защиты от антивирусных программ и параметры защиты в режиме реального времени.|
|[Onboard to Microsoft Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |На [ **этапе onboard** вы](switch-to-microsoft-defender-onboard.md)на борту устройств в Microsoft Defender для конечной точки и убедитесь, что эти устройства общаются с Microsoft Defender для конечной точки. Наконец, необходимо удалить существующее решение защиты конечной точки и убедиться, что защита с помощью антивируса Microsoft Defender & Microsoft Defender для конечной точки находится в активном режиме. |

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

- Приступить к [подготовке к миграции](switch-to-microsoft-defender-prepare.md).
