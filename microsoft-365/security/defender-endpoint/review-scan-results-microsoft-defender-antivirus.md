---
title: Просмотр результатов проверки авт.) Microsoft Defender
description: Просмотр результатов сканирования с помощью Microsoft Endpoint Configuration Manager, Microsoft Intune или Безопасность Windows приложения
keywords: результаты сканирования, исправление, полное сканирование, быстрое сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: bc7c84e089b08c440512f8a8bf7583f41394f2ca
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007641"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Проверка антивирусная программа в Microsoft Defender результатов сканирования

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

После завершения антивирусная программа в Microsoft Defender проверки, будь то по [](run-scan-microsoft-defender-antivirus.md) требованию или запланированное [сканирование,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)результаты записывают, и вы можете просмотреть результаты. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Использование диспетчера конфигурации для проверки результатов сканирования

Узнайте, [как отслеживать состояние Endpoint Protection.](/configmgr/protect/deploy-use/monitor-endpoint-protection)

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>Использование cmdlets PowerShell для проверки результатов сканирования

Следующий кодлет возвращает каждое обнаружение на конечной точке. Если существует несколько обнаружения одной и той же угрозы, каждое обнаружение будет перечислены отдельно, в зависимости от времени каждого обнаружения:

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="снимок экрана cmdlets и выходов PowerShell":::

Можно указать, чтобы ограничить выход только для обнаружения `-ThreatID` определенной угрозы.

Если вы хотите перечислить обнаружения угроз, но объединить обнаружения одной и той же угрозы в один элемент, можно использовать следующий cmdlet:

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="Код PowerShell":::

Дополнительные сведения об использовании PowerShell с антивирусной программой в Microsoft Defender см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Используйте Windows управления (WMI) для проверки результатов сканирования

Используйте [ **метод Get** классов **MSFT_MpThreat** **MSFT_MpThreatDetection.**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Статьи по теме

- [Настройка, инициирование и проверка результатов антивирусная программа в Microsoft Defender и исправлений](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)