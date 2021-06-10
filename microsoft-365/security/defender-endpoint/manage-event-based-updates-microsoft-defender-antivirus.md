---
title: Применение антивирусная программа в Microsoft Defender обновлений после определенных событий
description: Управление тем, антивирусная программа в Microsoft Defender применяет обновления разведки безопасности после запуска или получения отчетов об обнаружении с облачными данными.
keywords: обновления, защита, силовые обновления, события, запуск, проверка последних уведомлений
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 624e32bfebfce02021f1dcb1dbdde9446472239a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274704"
---
# <a name="manage-event-based-forced-updates"></a>Управление принудительными обновлениями на основе событий

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

антивирусная программа в Microsoft Defender позволяет определить, должны ли обновления (или не должны) возникать после определенных событий, например при запуске или после получения определенных отчетов от службы защиты с облачной доставкой.

## <a name="check-for-protection-updates-before-running-a-scan"></a>Проверка обновлений защиты перед запуском сканирования

Вы можете использовать Microsoft Endpoint Configuration Manager, групповые политики, powerShell и WMI, чтобы заставить антивирусная программа в Microsoft Defender проверять и скачивать обновления защиты перед запуском запланированного сканирования.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Используйте диспетчер конфигурации для проверки обновлений защиты перед запуском сканирования

1. На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ,  которые необходимо изменить (щелкните Активы и соответствие требованиям в области навигации слева, а затем разогнайте дерево до Endpoint Protection  >    >  **antimalware Policies**)

2. Перейдите в раздел **Запланированные** проверки и установите **Проверку** последних обновлений разведки безопасности перед запуском проверки **на да**.

3. Нажмите кнопку **ОК**.

4. [Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>Используйте групповую политику для проверки обновлений защиты перед запуском сканирования

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **Политики,** а **затем административные шаблоны**.

4. Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **сканирование.**

5. Дважды **щелкните Проверить последние** определения вирусов и программ-шпионов перед запуском запланированного сканирования и установите параметр **Включено**.

6. Нажмите кнопку **ОК**.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>Перед запуском сканирования используйте cmdlets PowerShell для проверки обновлений защиты

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/index).

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Используйте Windows управления (WMI) для проверки обновлений защиты перед запуском сканирования

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
CheckForSignaturesBeforeRunningScan
```

Дополнительные сведения см. [в Защитник Windows API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="check-for-protection-updates-on-startup"></a>Проверка обновлений защиты при запуске

Можно использовать групповую политику для антивирусная программа в Microsoft Defender проверки и загрузки обновлений защиты при работе компьютера.

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **Политики,** а **затем административные шаблоны**.

4. Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **обновлений разведки безопасности.**

5. Дважды **щелкните Проверьте последние** определения вирусов и программ-шпионов при запуске и установите параметр **Включено**. 

6. Нажмите кнопку **ОК**.

Можно также использовать групповую политику, PowerShell или WMI для настройки антивирусная программа в Microsoft Defender для проверки обновлений при запуске, даже если она не запущена.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Используйте групповую политику для скачивания обновлений, антивирусная программа в Microsoft Defender нет

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **Политики,** а **затем административные шаблоны**.

4. Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **обновлений разведки безопасности.**

5. Дважды **щелкните Инициировать обновление** сведении о безопасности при запуске и установите параметр **Включено.**

6. Нажмите кнопку **ОК**.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Используйте cmdlets PowerShell для скачивания обновлений, антивирусная программа в Microsoft Defender нет

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

Дополнительные сведения см. в дополнительных сведениях о том, как использовать [cmdlets PowerShell для](use-powershell-cmdlets-microsoft-defender-antivirus.md) управления антивирусная программа в Microsoft Defender и [defender](/powershell/module/defender/index) для получения дополнительных сведений о том, как использовать PowerShell с антивирусная программа в Microsoft Defender.

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Используйте Windows управления (WMI) для скачивания обновлений, антивирусная программа в Microsoft Defender нет

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

Дополнительные сведения см. [в Защитник Windows API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>Разрешить ad hoc changes to protection based on cloud-delivered protection

Microsoft Defender AV может вносить изменения в свою защиту на основе облачной защиты. Такие изменения могут происходить вне обычных или запланированных обновлений защиты.

Если у вас включена облачная защита, Microsoft Defender AV отправляет файлы, подозрительные для Защитник Windows облака. Если облачная служба сообщает о том, что файл вредоносный, а файл обнаружен в недавнем обновлении защиты, можно использовать групповую политику для настройки microsoft Defender AV для автоматического получения этого обновления защиты. Также можно применить другие важные обновления защиты.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>Использование групповой политики для автоматической загрузки последних обновлений на основе облачной защиты

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **Политики,** а **затем административные шаблоны**.

4. Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **обновлений разведки безопасности.**

5. Дважды **щелкните Разрешить обновления** сведении о безопасности в режиме реального времени на основе отчетов в Microsoft MAPS и установите параметр **Включено**. Нажмите кнопку **ОК**.

6. **Разрешить уведомления для отключения отчетов** на основе определений в Microsoft MAPS и установить параметр **Включено**. Нажмите кнопку **ОК**.
    
> [!NOTE]
> **Разрешение уведомлений для отключения** отчетов на основе определений позволяет Microsoft MAPS отключить эти определения, которые, как известно, вызывают ложные сообщения. Для работы этой функции необходимо настроить компьютер, чтобы присоединиться к Microsoft MAPS.

## <a name="see-also"></a>См. также

- [Развертывание антивирусная программа в Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Управление загрузкой и приложением обновлений защиты](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)