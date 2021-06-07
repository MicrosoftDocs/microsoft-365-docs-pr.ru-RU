---
title: Блокировка с учетом поведения клиента
description: Блокировка поведения клиента является частью возможностей поведенческой блокировки и сдерживания в Microsoft Defender for Endpoint
keywords: поведенческая блокировка, быстрая защита, поведение клиента, Microsoft Defender для endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 4e416aa9484f251280649035247a59dcc82ce750
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795962"
---
# <a name="client-behavioral-blocking"></a>Блокировка с учетом поведения клиента

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Обзор

Клиентская поведенческая блокировка является компонентом [возможностей](behavioral-blocking-containment.md) блокировки и сдерживания поведения в Защитнике для конечной точки. Поскольку подозрительные действия обнаруживаются на устройствах (также именуются клиентами или конечными точками), артефакты (например, файлы или приложения) блокируются, проверяются и устраняются автоматически. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Облачная и клиентская защита":::

Защита от антивирусов лучше всего работает в паре с облачной защитой.

## <a name="how-client-behavioral-blocking-works"></a>Как работает блокировка поведения клиента

[антивирусная программа в Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) может обнаруживать подозрительные действия, вредоносный код, атаки без файлов и в памяти и другие действия на устройстве. При обнаружении подозрительного поведения антивирусная программа в Microsoft Defender отслеживает и отправляет эти подозрительные действия и деревья процессов в службу защиты облаков. Машинное обучение различает вредоносные приложения и хорошее поведение в миллисекунд и классифицирует каждый артефакт. Почти в режиме реального времени, как только артефакт будет обнаружен вредоносным, он блокируется на устройстве. 

При обнаружении подозрительного [](alerts-queue.md) поведения создается оповещение, которое отображается в Центр безопасности в Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

Клиентская поведенческая блокировка эффективна, так как она не только помогает предотвратить начало атаки, но и помогает остановить приступив к выполнению. Кроме того, при блокировке [циклов](feedback-loop-blocking.md) обратной связи (еще одна возможность блокировки и сдерживания поведения) атаки предотвращаются на других устройствах в организации.

## <a name="behavior-based-detections"></a>Обнаружение на основе поведения

Обнаружения на основе поведения называются в соответствии с [матрицей ATT MITRE&CK для](https://attack.mitre.org/matrices/enterprise)Enterprise . Конвенция именования помогает определить стадию атаки, на которой было отмечено вредоносное поведение:


|Tactic |   Имя угрозы обнаружения |
|----|----|
|Начальный доступ | `Behavior:Win32/InitialAccess.*!ml` |
|Выполнение  | `Behavior:Win32/Execution.*!ml` |
|Упорство    | `Behavior:Win32/Persistence.*!ml` |
|Эскалация привилегий   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|Уклонение от защиты    | `Behavior:Win32/DefenseEvasion.*!ml` |
|Доступ к учетным данным  | `Behavior:Win32/CredentialAccess.*!ml` |
|Обнаружение  | `Behavior:Win32/Discovery.*!ml` |
|Lateral Movement | `Behavior:Win32/LateralMovement.*!ml` |
|Collection |   `Behavior:Win32/Collection.*!ml` |
|Команда и управление | `Behavior:Win32/CommandAndControl.*!ml` |
|Exfiltration   | `Behavior:Win32/Exfiltration.*!ml` |
|Влияние | `Behavior:Win32/Impact.*!ml` |
|Uncategorized  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> Дополнительные данные о конкретных угрозах см. в недавней **[глобальной активности угроз.](https://www.microsoft.com/wdsi/threats)**


## <a name="configuring-client-behavioral-blocking"></a>Настройка клиентской поведенческой блокировки

Если ваша организация использует Defender для конечной точки, клиентская поведенческая блокировка включена по умолчанию. Однако, чтобы воспользоваться всеми возможностями Defender для [](behavioral-blocking-containment.md)конечной точки, включая поведенческую блокировку и сдерживание, убедитесь, что включены и настроены следующие функции и возможности Defender для конечной точки:

- [Базовые показатели Defender для конечной точки](configure-machines-security-baseline.md)

- [Устройства, на борту для Защитника для конечной точки](onboard-configure.md)

- [EDR в режиме блокировки](edr-in-block-mode.md)

- [Сокращение направлений атак](attack-surface-reduction.md)

- [Защита нового поколения](configure-microsoft-defender-antivirus-features.md) (антивирусные, антивирусные и другие возможности защиты от угроз)

