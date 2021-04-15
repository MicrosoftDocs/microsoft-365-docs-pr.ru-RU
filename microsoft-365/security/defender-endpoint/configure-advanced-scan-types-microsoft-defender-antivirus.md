---
title: Настройка параметров сканирования для microsoft Defender AV
description: Вы можете настроить microsoft Defender AV для сканирования файлов хранения электронной почты, точек для архивирования или репараса, сетевых файлов и архивных файлов (например, файлов zip).
keywords: расширенные проверки, сканирование, электронная почта, архив, почтовый индекс, rar, архив, сканирование репара
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 72d5024446e56cc7fa1d94a7b9402cbe898db2a8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764859"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Настройка параметров сканирования антивирусной программы в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Настройка параметров сканирования с помощью Microsoft Intune

Дополнительные сведения см. в настройках параметров ограничения устройств [в Microsoft Intune](/intune/device-restrictions-configure) и [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Используйте Microsoft Endpoint Manager для настройки параметров сканирования

Сведения о настройке Microsoft Endpoint Manager (текущая ветвь) см. в материале "Создание и развертывание политик противомалярийных [программ".](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)

## <a name="use-group-policy-to-configure-scanning-options"></a>Использование групповой политики для настройки параметров сканирования

Настройка параметров групповой политики, описанных в следующей таблице:

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.

3. Расширь дерево до компонентов **Windows > антивируса Microsoft Defender** и далее в указанном ниже расположении. 

4. Дважды щелкните параметр **политики,** указанный в таблице ниже, и установите параметр в нужную конфигурацию. Нажмите **кнопку ОК** и повторите для любых других параметров.

Описание | Расположение и параметр | Параметр по умолчанию (если не настроен) | Параметр PowerShell `Set-MpPreference` или свойство WMI для `MSFT_MpPreference` класса
---|---|---|---
Сканирование электронной почты [См. ограничения сканирования электронной почты](#ref1)| Сканирование > включив сканирование электронной почты | Отключена | `-DisableEmailScanning`
Точки [репаража сканирования](/windows/win32/fileio/reparse-points) | Сканирование > включив сканирование точеи репара | Отключена | Недоступно
Сканирование сетевых дисков с картой | Сканирование > полное сканирование на картах сетевых дисков | Отключена | `-DisableScanningMappedNetworkDrivesForFullScan`
 Сканирование архивных файлов (например, файлов zip или .rar). Список [исключений расширений](configure-extension-file-exclusions-microsoft-defender-antivirus.md) будет иметь приоритет над этим параметром. | Сканирование > архивных файлов | Включено | `-DisableArchiveScanning`
Сканирование файлов в сети | Сканирование > сетевых файлов | Отключена | `-DisableScanningNetworkFiles`
Сканирование упакованных исполняемых исполняемых | Сканирование > упакованных исполняемых исполняемых | Включено | Недоступно
Сканирование съемных дисков только во время полного сканирования | Сканирование > съемных дисков | Отключена | `-DisableRemovableDriveScanning`
Укажите уровень подмостки в папке архива для сканирования | Сканирование > укажите максимальную глубину для сканирования архивных файлов | 0 | Недоступно
 Укажите максимальную нагрузку ЦП (в процентах) во время сканирования. Примечание. Это не жесткий предел, а руководство для двигателя сканирования, чтобы не превышать этот максимум в среднем. | Сканирование > укажите максимальный процент использования ЦП во время сканирования | 50 |  `-ScanAvgCPULoadFactor`
 Укажите максимальный размер (в килобайтах) архивных файлов, которые необходимо отсканировать. По **умолчанию, 0**, не применяется никаких ограничений | Сканирование > укажите максимальный размер отсканированных архивных файлов | Нет ограничений | Недоступно
 Настройка низкого приоритета ЦП для запланированных сканов | Сканирование > настройка низкого приоритета ЦП для запланированных сканов | Отключена | Недоступно
 
> [!NOTE]
> Если защита включена в режиме реального времени, файлы сканируют перед их доступом и выполнением. Область сканирования включает все файлы, включая файлы на съемных носите, таких как USB-диски. Если устройство, которое выполняет сканирование, имеет защиту в режиме реального времени или включено в режиме реального времени, сканирование также будет включать сетевые акции.

## <a name="use-powershell-to-configure-scanning-options"></a>Настройка параметров сканирования с помощью PowerShell

Дополнительные сведения о том, как использовать PowerShell с антивирусом [Microsoft](use-powershell-cmdlets-microsoft-defender-antivirus.md) Defender, см. в этой ссылке. [](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>Использование WMI для настройки параметров сканирования

Для использования классов WMI см. Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>Ограничения сканирования электронной почты

Сканирование электронной почты позволяет сканировать файлы электронной почты, используемые Outlook и другими почтовыми клиентами во время проверки по запросу и по расписанию. Также проверяются встроенные объекты в файле электронной почты (например, вложения и архивированные файлы). Следующие типы формата файлов можно отсканировать и по исправлению:

- DBX
- MBX
- MIME

PST-файлы, используемые в Outlook 2003 или более старше (где тип архива задают не-юникод) также будут отсканированы, но Защитник Windows не могут устранять угрозы, обнаруженные в PST-файлах.

Если антивирус Microsoft Defender обнаруживает угрозу внутри электронной почты, он покажет вам следующие сведения, которые помогут вам определить скомпрометированную электронную почту, чтобы вы могли устранять угрозу вручную:

- Тема письма
- Имя вложения

## <a name="related-topics"></a>Связанные статьи

- [Настройка, инициирование и проверка результатов проверки и устранения антивирусных программ Microsoft Defender](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Настройка и запуск проверки антивирусной программой в Microsoft Defender по требованию](run-scan-microsoft-defender-antivirus.md).
- [Настройка запланированных антивирусных сканов Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)