---
title: Запуск и настройка проверки по запросу в microsoft Defender AV
description: Запуск и настройка сканирования по запросу с помощью PowerShell, инструментов управления Windows или отдельно на конечных точках с помощью приложения Безопасности Windows
keywords: сканирование, по требованию, dos, intune, моментальное сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2f60bdb0bbd8b87895547e608b5c3c92414ea834
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691174"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Настройка и запуск антивирусных сканов Microsoft Defender по запросу

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Можно выполнить проверку по запросу на отдельных конечных точках. Эти проверки начнутся немедленно, и вы можете определить параметры для сканирования, такие как расположение или тип.

## <a name="quick-scan-versus-full-scan"></a>Быстрое сканирование по сравнению с полным сканированием

Быстрое сканирование позволяет просмотреть все расположения, в которых может быть зарегистрирована вредоносная программа, например ключи реестра и известные папки запуска Windows.

> [!IMPORTANT]
> Антивирус Microsoft Defender выполняется в контексте учетной записи [LocalSystem](/windows/win32/services/localsystem-account) при выполнении локального сканирования. Для сканирования сети используется контекст учетной записи устройства. Если учетная запись устройства домена не имеет соответствующих разрешений на доступ к этой совместной работе, проверка не будет работать. Убедитесь, что у устройства есть разрешения на доступ к сетевой сети.

В [](configure-real-time-protection-microsoft-defender-antivirus.md)сочетании с возможностью защиты в режиме реального времени , которая проверяет файлы при их открытиях и закрытии, а также при переходе пользователя в папку, быстрое сканирование обеспечивает высокий уровень защиты как для вредоносных программ, которые начинаются с системного, так и для вредоносных программ на уровне ядра.  

В большинстве случаев для обнаружения вредоносных программ, которые не были подхватлены защитой в режиме реального времени, достаточно быстрой проверки.

Полное сканирование может быть полезно для конечных точек, которые сообщили об угрозе вредоносных программ. Сканирование может определить, есть ли неактивные компоненты, которые требуют более тщательной очистки. Это идеальное решение, если ваша организация работает по запросу.

> [!NOTE]
> По умолчанию быстрые проверки запускаются на установленных съемных устройствах, например USB-накопителях.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Используйте Microsoft Endpoint Manager для запуска сканирования

1. Перейдите в центр администрирования диспетчера конечных точек Майкрософт () и [https://endpoint.microsoft.com](https://endpoint.microsoft.com) войдите в систему.
2. Выберите **антивирус безопасности**  >  **конечных точек**.
3. В списке вкладок выберите **windows 10 нездоровые конечные точки.**
4. Из представленного списка действий выберите **быстрое** сканирование или **полное сканирование.**

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Дополнительные сведения об использовании Microsoft Endpoint Manager для выполнения проверки см. в статью Задачи по борьбе с антивирусом и брандмауэром: как выполнить проверку по [запросу.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Используйте утилиту mpcmdrun.exe командной строки для запуска сканирования

Используйте следующий `-scan` параметр:

```console
mpcmdrun.exe -scan -scantype 1
```

Дополнительные сведения об использовании средства и дополнительных параметров, включая запуск полного сканирования или определение путей, см. в mpcmdrun.exe средства командной линии для настройки и управления антивирусом [Microsoft Defender.](command-line-arguments-microsoft-defender-antivirus.md)

## <a name="use-microsoft-intune-to-run-a-scan"></a>Используйте Microsoft Intune для запуска сканирования

1. Перейдите в центр администрирования диспетчера конечных точек Майкрософт () и [https://endpoint.microsoft.com](https://endpoint.microsoft.com) войдите в систему.
2. На боковой панели выберите **устройства > все устройства** и выберите устройство, которое необходимо сканировать.
3. Выберите **... Подробнее**. Из параметров выберите **быстрое сканирование** или **полное сканирование.**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>С помощью приложения Windows Security можно выполнить сканирование

См. [в приложении Run a scan in the Windows Security](microsoft-defender-security-center-antivirus.md) для инструкций по запуску сканирования на отдельных конечных точках.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Чтобы выполнить сканирование, используйте cmdlets PowerShell

Используйте следующий cmdlet:

```PowerShell
Start-MpScan
```

Дополнительные сведения о том, как использовать PowerShell с антивирусной программой Microsoft Defender, см. в см. в рублях Use [PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Использование инструкции по управлению Windows (WMI) для проверки

Используйте метод [ **Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) **класса MSFT_MpScan.**

Дополнительные сведения о том, какие параметры разрешены, см. в Защитник Windows [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>Статьи по теме

- [Настройка параметров антивирусного сканирования Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Настройка запланированных антивирусных сканов Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)