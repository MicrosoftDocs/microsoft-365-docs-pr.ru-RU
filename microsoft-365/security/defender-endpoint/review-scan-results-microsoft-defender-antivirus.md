---
title: Просмотр результатов проверки авт.) Microsoft Defender
description: Просмотрите результаты сканирования с помощью Microsoft Endpoint Configuration Manager, Microsoft Intune или приложения безопасности Windows
keywords: результаты сканирования, исправление, полное сканирование, быстрое сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8fe2810ce18589d3131aa17f25ccfb01ec26b892
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691209"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Просмотр результатов проверки антивирусных программ Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

После завершения антивирусного сканирования Защитника Майкрософт, [](run-scan-microsoft-defender-antivirus.md) будь то проверка по запросу или запланированное, [](scheduled-catch-up-scans-microsoft-defender-antivirus.md)результаты записывают, и вы можете просмотреть результаты. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Использование диспетчера конфигурации для проверки результатов сканирования

Узнайте, [как отслеживать состояние защиты конечных точек.](/configmgr/protect/deploy-use/monitor-endpoint-protection)

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>Использование cmdlets PowerShell для проверки результатов сканирования

Следующий кодлет возвращает каждое обнаружение на конечной точке. Если существует несколько обнаружения одной и той же угрозы, каждое обнаружение будет перечислены отдельно, в зависимости от времени каждого обнаружения:

```PowerShell
Get-MpThreatDetection
```

![снимок экрана cmdlets и выходов PowerShell](images/defender/wdav-get-mpthreatdetection.png)

Можно указать, чтобы ограничить выход только для обнаружения `-ThreatID` определенной угрозы.

Если вы хотите перечислить обнаружения угроз, но объединить обнаружения одной и той же угрозы в один элемент, можно использовать следующий cmdlet:

```PowerShell
Get-MpThreat
```

![скриншот PowerShell](images/defender/wdav-get-mpthreat.png)

Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Использование инструкции по управлению Windows (WMI) для проверки результатов сканирования

Используйте [ **метод Get** классов **MSFT_MpThreat** **MSFT_MpThreatDetection.**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Статьи по теме

- [Настройка, инициирование и проверка результатов проверки и устранения антивирусных программ Microsoft Defender](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)