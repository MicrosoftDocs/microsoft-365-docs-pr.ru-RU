---
title: Запуск и настройка сканирования по запросу в антивирусная программа в Microsoft Defender
description: Запуск и настройка сканирования по запросу с помощью PowerShell, Windows инструментов управления или отдельно на конечных точках с помощью Безопасность Windows приложения
keywords: сканирование, по требованию, dos, intune, моментальное сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 3ee37d7220527c9032b630e02258c684b6c860b3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878812"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Настройка и запуск проверки антивирусной программой в Microsoft Defender по требованию.

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Можно выполнить проверку по запросу на отдельных конечных точках. Эти проверки начнутся немедленно, и вы можете определить параметры для сканирования, такие как расположение или тип. При запуске сканирования можно выбрать один из трех типов: быстрое сканирование, полное сканирование и настраиваемая проверка. В большинстве случаев используйте быстрое сканирование. Быстрое сканирование позволяет просмотреть все расположения, в которых может быть зарегистрировано вредоносное ПО, например ключи реестра и известные папки Windows запуска. 

В сочетании с постоянной защитой в режиме реального времени, которая проверяет файлы при их открытиях и закрытии, а также при переходе пользователя в папку, быстрое сканирование помогает обеспечить надувную защиту от вредоносных программ, которые начинаются с системной и вредоносной программы на уровне ядра. В большинстве случаев достаточно быстрой проверки, что является рекомендуемой возможностью для планового или по требованию сканирования.  [Узнайте больше о типах сканирования.](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)

> [!IMPORTANT]
> антивирусная программа в Microsoft Defender выполняется в контексте учетной записи [LocalSystem](/windows/win32/services/localsystem-account) при выполнении локального сканирования. Для сканирования сети используется контекст учетной записи устройства. Если учетная запись устройства домена не имеет соответствующих разрешений на доступ к этой совместной работе, проверка не будет работать. Убедитесь, что у устройства есть разрешения на доступ к сетевой сети.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Использование Microsoft Endpoint Manager для запуска сканирования

1. Перейдите в центр администрирования Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите в систему.

2. Выберите **антивирус безопасности**  >  **конечных точек**.

3. В списке вкладок выберите Windows 10 **нездоровые конечные точки.**

4. Из представленного списка действий выберите **быстрый скан** (рекомендуется) или **полное сканирование.**

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Дополнительные сведения об использовании Microsoft Endpoint Manager для выполнения проверки см. в статью [Antimalware and firewall tasks: How to perform an on-demand scan.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Используйте утилиту mpcmdrun.exe командной строки для запуска сканирования

Используйте следующий `-scan` параметр:

```console
mpcmdrun.exe -scan -scantype 1
```

Дополнительные сведения об использовании средства и дополнительных параметров, включая запуск полного сканирования или определение путей, см. в mpcmdrun.exe средства командной линии для настройки и управления [антивирусная программа в Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).

## <a name="use-microsoft-intune-to-run-a-scan"></a>Используйте Microsoft Intune для запуска сканирования

1. Перейдите в центр администрирования Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите в систему.

2. На боковой панели выберите **устройства**  >  **всех устройств** и выберите устройство, которое необходимо сканировать.

3. Выберите **... Подробнее**. Из параметров выберите **быстрый скан** (рекомендуется) или **полное сканирование.**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Используйте приложение Безопасность Windows для запуска сканирования

См. [в приложении Run a scan in the Безопасность Windows](microsoft-defender-security-center-antivirus.md) инструкции по запуску сканирования на отдельных конечных точках.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Чтобы выполнить сканирование, используйте cmdlets PowerShell

Используйте следующий cmdlet:

```PowerShell
Start-MpScan
```

Дополнительные сведения о том, как использовать PowerShell с антивирусная программа в Microsoft Defender, см. в см. в рублях Use [PowerShell cmdlets to configure and run антивирусная программа в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Defender.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Используйте Windows управления (WMI) для запуска сканирования

Используйте метод [ **Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) **класса MSFT_MpScan.**

Дополнительные сведения о том, какие параметры разрешены, см. в Защитник Windows [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

