---
title: Блокировка с учетом поведения клиента
description: Блокировка поведения клиента является частью возможностей поведенческой блокировки и сдерживания в Microsoft Defender for Endpoint
keywords: поведенческая блокировка, быстрая защита, поведение клиентов, ATP Защитника Майкрософт, защитник Майкрософт для конечной точки
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
ms.openlocfilehash: 48929d0e2b0c932d37cb5d29783712d00b17117f
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904156"
---
# <a name="client-behavioral-blocking"></a>Блокировка с учетом поведения клиента

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Обзор

Клиентская поведенческая блокировка является компонентом [возможностей](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) блокировки и сдерживания поведения в Защитнике для конечной точки. Поскольку подозрительные действия обнаруживаются на устройствах (также именуются клиентами или конечными точками), артефакты (например, файлы или приложения) блокируются, проверяются и устраняются автоматически. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Облачная и клиентская защита":::

Защита от антивирусов лучше всего работает в паре с облачной защитой.

## <a name="how-client-behavioral-blocking-works"></a>Как работает блокировка поведения клиента

[Антивирус Microsoft Defender может](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) обнаруживать подозрительные действия, вредоносный код, атаки без файлов и в памяти и другие действия на устройстве. При обнаружении подозрительных поведений антивирус Microsoft Defender отслеживает и отправляет эти подозрительные действия и деревья процессов в службу защиты облаков. Машинное обучение различает вредоносные приложения и хорошее поведение в миллисекунд и классифицирует каждый артефакт. Почти в режиме реального времени, как только артефакт будет обнаружен вредоносным, он блокируется на устройстве. 

При обнаружении подозрительного [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) поведения создается оповещение, которое отображается в Центре безопасности Защитника Майкрософт ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

Клиентская поведенческая блокировка эффективна, так как она не только помогает предотвратить начало атаки, но и помогает остановить приступив к выполнению. Кроме того, при блокировке [циклов](feedback-loop-blocking.md) обратной связи (еще одна возможность блокировки и сдерживания поведения) атаки предотвращаются на других устройствах в организации.

## <a name="behavior-based-detections"></a>Обнаружение на основе поведения

Обнаружения на основе поведения называются в соответствии с [матрицей ATT MITRE&CK для предприятия](https://attack.mitre.org/matrices/enterprise). Конвенция именования помогает определить стадию атаки, на которой было отмечено вредоносное поведение:


|Tactic |   Имя угрозы обнаружения |
|----|----|
|Начальный доступ | Поведение:Win32/InitialAccess.*!ml |
|Выполнение  | Поведение:Win32/Execution.*!ml |
|Упорство    | Поведение:Win32/Persistence.*!ml |
|Эскалация привилегий   | Поведение:Win32/PrivilegeEscalation.*!ml |
|Уклонение от защиты    | Поведение:Win32/DefenseEvasion.*!ml |
|Доступ к учетным данным  | Поведение:Win32/CredentialAccess.*!ml |
|Discovery  | Поведение:Win32/Discovery.*!ml |
|Lateral Movement | Поведение:Win32/LateralMovement.*!ml |
|Collection |   Поведение:Win32/Collection.*!ml |
|Команда и управление | Поведение:Win32/CommandAndControl.*!ml |
|Exfiltration   | Поведение:Win32/Exfiltration.*!ml |
|Влияние | Поведение:Win32/Impact.*!ml |
|Uncategorized  | Поведение:Win32/Generic.*!ml |

> [!TIP]
> Дополнительные данные о конкретных угрозах см. в недавней **[глобальной активности угроз.](https://www.microsoft.com/wdsi/threats)**


## <a name="configuring-client-behavioral-blocking"></a>Настройка клиентской поведенческой блокировки

Если ваша организация использует Defender для конечной точки, клиентская поведенческая блокировка включена по умолчанию. Однако, чтобы воспользоваться всеми возможностями Defender для [](behavioral-blocking-containment.md)конечной точки, включая поведенческую блокировку и сдерживание, убедитесь, что включены и настроены следующие функции и возможности Defender для конечной точки:

- [Базовые показатели Defender для конечной точки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Устройства, на борту для Защитника для конечной точки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR в режиме блокировки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Сокращение направлений атак](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Защита нового поколения](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (антивирус)

## <a name="related-articles"></a>Статьи по теме

- [Блокировка с учетом поведения и автономность](behavioral-blocking-containment.md)

- [Блокировка циклов обратной связи](feedback-loop-blocking.md)

- [(Блог) Блокировка и сдерживание поведения: преобразование оптики в защиту](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Полезные ресурсы Defender для конечных точек](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
