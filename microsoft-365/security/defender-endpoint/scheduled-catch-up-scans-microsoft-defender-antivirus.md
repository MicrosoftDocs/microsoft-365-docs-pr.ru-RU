---
title: Регулярное быстрое и полное сканирование с помощью антивируса Microsoft Defender
description: Настройка повторяющихся (запланированных) сканирований, в том числе при их запуске и в качестве полного или быстрого сканирования.
keywords: быстрое сканирование, полное сканирование, быстрый vs полный, сканирование расписания, ежедневно, еженедельно, время, запланированное, повторяющиеся, регулярные
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691302"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Настройка запланированных быстрых или полных антивирусных сканов Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Антивирус Microsoft Defender по умолчанию проверяет обновление за 15 минут до времени запланированного сканирования. Для [переопределения](manage-protection-update-schedule-microsoft-defender-antivirus.md) этого по умолчанию можно управлять расписанием загрузки обновлений защиты. 

Помимо постоянной защиты в режиме [](run-scan-microsoft-defender-antivirus.md) реального времени и проверки по запросу можно настроить регулярные запланированные проверки. 

Вы можете настроить тип сканирования, когда должно происходить сканирование, и [](manage-protection-updates-microsoft-defender-antivirus.md) если сканирование должно происходить после обновления защиты или если используется конечная точка. Вы также можете указать, когда должны происходить специальные проверки для завершения восстановления.

В этой статье описывается настройка запланированных сканов с помощью групповая политика, cmdlets PowerShell и WMI. Вы также можете настроить проверки расписания с [помощью Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) или Microsoft [Intune.](/mem/intune/configuration/device-restrictions-windows-10)

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>Настройка параметров групповой политики, описанных в этой статье

1.  На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

3.  В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

4.  Щелкните **административные шаблоны**.

5.  Расширь дерево до компонентов **Windows > антивируса Microsoft Defender** и далее в указанном ниже расположении. 

6. Дважды щелкните параметр **политики,** указанный в таблице ниже, и установите параметр в нужную конфигурацию. 

7. Нажмите **кнопку ОК** и повторите для любых других параметров.

Также см. [раздел Управление,](manage-protection-update-schedule-microsoft-defender-antivirus.md) когда обновления защиты должны быть загружены и применены, и Запретить или разрешить пользователям локально изменять [параметры политик.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Быстрое сканирование по сравнению с полным сканированием и пользовательским сканированием

При настройках плановой проверки можно настроить полное или быстрое сканирование.

При быстром сканировании просматриваются все расположения, в которых могут быть зарегистрированы вредоносные программы, например ключи реестра и известные папки запуска Windows. 

В сочетании с возможностью защиты в режиме реального [времени,](configure-real-time-protection-microsoft-defender-antivirus.md) которая проверяет файлы при их открытиях и закрытии, а также при переходе пользователя в папку, быстрое сканирование помогает обеспечить широкое освещение вредоносных программ, которые начинаются с системной и вредоносной программы на уровне ядра.  

В большинстве случаев это означает, что для обнаружения вредоносных программ, которые не были подхватлены средствами защиты в режиме реального времени, достаточно быстрой проверки.

Полное сканирование может быть полезно для конечных точек, которые столкнулись с угрозой вредоносных программ, чтобы определить, есть ли какие-либо неактивные компоненты, которые требуют более тщательной очистки. В этом случае при запуске проверки по запросу может потребоваться полное [сканирование.](run-scan-microsoft-defender-antivirus.md)

Настраиваемая проверка позволяет указать файлы и папки для сканирования, например USB-накопитель. 

>[!NOTE]
>По умолчанию быстрые проверки запускаются на установленных съемных устройствах, например USB-накопителях.

## <a name="set-up-scheduled-scans"></a>Настройка запланированных сканов

Запланированные проверки будут запускаться в течение дня и времени, за который вы указываете. Для настройки запланированных сканов можно использовать групповую политику, PowerShell и WMI.

>[!NOTE]
>Если компьютер отключен и запущен на батарее во время запланированного полного сканирования, запланированное сканирование остановится с событием 1002, в котором говорится, что проверка остановлена до завершения. Антивирус Microsoft Defender запустит полное сканирование в назначенное время.

### <a name="use-group-policy-to-schedule-scans"></a>Использование групповой политики для расписания сканирования

|Расположение | Setting | Описание | Параметр по умолчанию (если не настроен) |
|:---|:---|:---|:---|
|Проверка | Укажите тип сканирования, который необходимо использовать для запланированного сканирования | Быстрое сканирование |
|Проверка | Укажите день недели для запуска запланированного сканирования | Укажите день (или никогда) для запуска сканирования. | Никогда |
|Проверка | Укажите время суток для запуска запланированного сканирования | Укажите количество минут после полуночи (например, введите **60** для 1:00). | 02:00. |
|Root | Рандомизация запланированного времени задач |В антивирусе Microsoft Defender: рандомизируйте время начала сканирования с интервалом от 0 до 4 часов. <br>В FEP/SCEP: рандомизировать любой интервал плюс или минус 30 минут. Это может быть полезно в развертываниях VM или VDI. | Включено |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Использование cmdlets PowerShell для расписания сканирования

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Использование инструкции по управлению Windows (WMI) для расписания сканирования

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Дополнительные сведения и допустимые параметры см. в следующих сведениях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>Запуск запланированных сканов только в том случае, если конечная точка не используется

Вы можете настроить запланированное сканирование только при включении конечной точки, но не в использовании с групповой политикой, PowerShell или WMI.

> [!NOTE]
> Эти проверки не будут соблюдать конфигурацию регулирования ЦП и в полной мере использовать ресурсы, доступные для выполнения проверки как можно быстрее.

### <a name="use-group-policy-to-schedule-scans"></a>Использование групповой политики для расписания сканирования

|Расположение | Setting | Описание | Параметр по умолчанию (если не настроен) |
|:---|:---|:---|:---|
|Проверка | Запуск запланированного сканирования только в том случае, если компьютер находится на компьютере, но не используется | Запланированные проверки не будут запускаться, если компьютер не работает, но не используется | Включено |

### <a name="use-powershell-cmdlets"></a>Использование cmdlets PowerShell

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.

### <a name="use-windows-management-instruction-wmi"></a>Использование инструкции по управлению Windows (WMI)

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
ScanOnlyIfIdleEnabled
```

Дополнительные сведения и допустимые параметры см. в следующих сведениях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Настройка при запуске полного сканирования для завершения восстановления

Для устранения и устранения некоторых угроз может потребоваться полное сканирование. Вы можете запланировать, когда эти проверки должны происходить с помощью групповой политики, PowerShell или WMI.

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>Использование групповой политики для расписания сканов, необходимых для восстановления

| Расположение | Setting | Описание | Параметр по умолчанию (если не настроен) |
|---|---|---|---|
|Исправление | Укажите день недели для выполнения запланированного полного сканирования для завершения восстановления | Укажите день (или никогда) для запуска сканирования. | Никогда |
|Исправление | Укажите время суток для выполнения запланированного полного сканирования, чтобы завершить исправление | Укажите количество минут после полуночи (например, введите **60** в час ночи) | 02:00. |

### <a name="use-powershell-cmdlets"></a>Использование cmdlets PowerShell

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.

### <a name="use-windows-management-instruction-wmi"></a>Использование инструкции по управлению Windows (WMI)

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Дополнительные сведения и допустимые параметры см. в следующих сведениях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a>Настройка ежедневных быстрых сканов

Вы можете включить ежедневное быстрое сканирование, которое можно выполнить в дополнение к другим запланированным проверкам с помощью групповой политики, PowerShell или WMI.


### <a name="use-group-policy-to-schedule-daily-scans"></a>Использование групповой политики для расписания ежедневных сканов


|Расположение | Setting | Описание | Параметр по умолчанию (если не настроен) |
|:---|:---|:---|:---|
|Проверка | Укажите интервал для быстрого сканирования в день | Укажите, сколько часов должно быть у вас до следующего быстрого сканирования. Например, чтобы выполнить каждые два часа, введите **2**, раз в день введите **24**. Введите **0,** чтобы никогда не запускать ежедневное быстрое сканирование. | Никогда |
|Проверка | Укажите время ежедневного быстрого сканирования | Укажите количество минут после полуночи (например, введите **60** в час ночи) | 02:00. |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>Использование cmdlets PowerShell для расписания ежедневных сканов

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Использование инструкции по управлению Windows (WMI) для расписания ежедневных сканов

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
ScanScheduleQuickScanTime
```

Дополнительные сведения и допустимые параметры см. в следующих сведениях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>Включить сканирование после обновления защиты

Проверку можно принудить к проверке после [каждого обновления защиты](manage-protection-updates-microsoft-defender-antivirus.md) с помощью групповой политики.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Использование групповой политики для расписания сканирования после обновления защиты

|Расположение | Setting | Описание | Параметр по умолчанию (если не настроен)|
|:---|:---|:---|:---|
|Обновления подписи | Включив сканирование после обновления сведении безопасности | Сканирование будет происходить сразу после загрузки нового обновления защиты | Включено |

## <a name="see-also"></a>См. также
- [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Настройка и запуск антивирусных сканов Microsoft Defender по запросу](run-scan-microsoft-defender-antivirus.md)
- [Настройка параметров антивирусного сканирования Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Управление обновлениями антивируса Microsoft Defender и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Управление загрузкой и приложением обновлений защиты](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)