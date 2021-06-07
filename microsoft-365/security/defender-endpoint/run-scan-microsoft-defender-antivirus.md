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
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789175"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Настройка и запуск проверки антивирусной программой в Microsoft Defender по требованию.

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Можно выполнить проверку по запросу на отдельных конечных точках. Эти проверки начнутся немедленно, и вы можете определить параметры для сканирования, такие как расположение или тип.

## <a name="quick-scan-versus-full-scan"></a>Быстрое сканирование по сравнению с полным сканированием

Быстрое сканирование позволяет просмотреть все расположения, в которых может быть зарегистрировано вредоносное ПО, например ключи реестра и известные папки Windows запуска.

> [!IMPORTANT]
> антивирусная программа в Microsoft Defender выполняется в контексте учетной записи [LocalSystem](/windows/win32/services/localsystem-account) при выполнении локального сканирования. Для сканирования сети используется контекст учетной записи устройства. Если учетная запись устройства домена не имеет соответствующих разрешений на доступ к этой совместной работе, проверка не будет работать. Убедитесь, что у устройства есть разрешения на доступ к сетевой сети.

В сочетании [с возможностью](configure-real-time-protection-microsoft-defender-antivirus.md)защиты в режиме реального времени быстрое сканирование позволяет обеспечить широкое освещение вредоносных программ, которые начинаются с вредоносных программ на уровне системы и на уровне ядра. Всегда в режиме реального времени файлы защиты рассматриваются при их открытом и закрытом режиме, а также при переходе пользователя в папку. По умолчанию быстрые проверки запускаются на установленных съемных устройствах, например USB-накопителях. В большинстве случаев для обнаружения вредоносных программ, которые не были подхватлены защитой в режиме реального времени, достаточно быстрой проверки.

Полное сканирование может быть полезно при сообщении об угрозе вредоносных программ на конечной точке. Проверка может определить, есть ли какие-либо неактивные компоненты, которые требуют более тщательной очистки. Однако Корпорация Майкрософт обычно рекомендует использовать быстрые проверки вместо полного сканирования. Полное сканирование может занять несколько часов или дней в зависимости от количества и типа данных, которые необходимо отсканировать. 

> [!TIP]
> Дополнительные дополнительные информацию о различиях между быстрым и полным сканированием см. в обзоре Быстрого сканирования и полного сканирования [и настраиваемой проверки.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Использование Microsoft Endpoint Manager для запуска сканирования

1. Перейдите в центр администрирования Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите в систему.
2. Выберите **антивирус безопасности**  >  **конечных точек**.
3. В списке вкладок выберите Windows 10 **нездоровые конечные точки.**
4. Из представленного списка действий выберите **быстрое** сканирование или **полное сканирование.**

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
2. На боковой панели выберите **устройства > все устройства** и выберите устройство, которое необходимо сканировать.
3. Выберите **... Подробнее**. Из параметров выберите **быстрое сканирование** или **полное сканирование.**

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

## <a name="related-articles"></a>Связанные статьи

- [Настройка параметров сканирования антивирусной программы в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Настройка запланированных антивирусная программа в Microsoft Defender сканирования](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)