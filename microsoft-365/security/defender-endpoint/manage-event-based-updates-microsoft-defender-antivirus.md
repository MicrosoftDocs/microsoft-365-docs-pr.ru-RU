---
title: Применение обновлений антивируса Microsoft Defender после определенных событий
description: Управление тем, как антивирус Microsoft Defender применяет обновления аналитики безопасности после запуска или получения отчетов об обнаружении с облачными данными.
keywords: обновления, защита, силовые обновления, события, запуск, проверка последних уведомлений
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b9f09878c645d54aadca21fe01749a0e73939c5f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691044"
---
# <a name="manage-event-based-forced-updates"></a>Управление вынужденными обновлениями на основе событий

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Антивирус Microsoft Defender позволяет определить, должны ли обновления (или не должны) происходить после определенных событий, например при запуске или после получения определенных отчетов от службы защиты с облачной доставкой.

## <a name="check-for-protection-updates-before-running-a-scan"></a>Проверка обновлений защиты перед запуском сканирования

Вы можете использовать Microsoft Endpoint Configuration Manager, групповые политики, команды PowerShell и WMI, чтобы заставить антивирус Microsoft Defender проверять и скачивать обновления защиты перед запуском запланированного сканирования.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Используйте диспетчер конфигурации для проверки обновлений защиты перед запуском сканирования

1. На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ, которые необходимо изменить (нажмите кнопку Активы и соответствие требованиям в области навигации слева, а затем расширите дерево до Обзор политики защиты конечных   >    >  точек)

2. Перейдите в раздел **Запланированные** проверки и установите **Проверку** последних обновлений разведки безопасности перед запуском проверки **на да**.

3. Нажмите кнопку **ОК**.

4. [Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>Используйте групповую политику для проверки обновлений защиты перед запуском сканирования

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **Политики,** а **затем административные шаблоны**.

4. Расширь дерево до **компонентов**  >  **Антивирусной проверки Microsoft Defender**  >  **Microsoft** Defender.

5. Дважды **щелкните Проверить последние** определения вирусов и программ-шпионов перед запуском запланированного сканирования и установите параметр **Включено**.

6. Нажмите кнопку **ОК**.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>Перед запуском сканирования используйте cmdlets PowerShell для проверки обновлений защиты

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

Дополнительные сведения см. в дополнительных сведениях, которые [см.](/powershell/module/defender/index)в см. в рублях [Использование cmdlets PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) для настройки и запуска антивирусных и защитников Microsoft Defender.

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Используйте инструкцию по управлению Windows (WMI) для проверки обновлений защиты перед запуском сканирования

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
CheckForSignaturesBeforeRunningScan
```

Дополнительные сведения см. [в Защитник Windows API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="check-for-protection-updates-on-startup"></a>Проверка обновлений защиты при запуске

С помощью групповой политики можно заставить антивирус Microsoft Defender проверять и скачивать обновления защиты при работе компьютера.

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **Политики,** а **затем административные шаблоны**.

4. Расширь дерево до **компонентов Microsoft**  >  **Defender Antivirus** Security Intelligence  >  **Updates**.

5. Дважды **щелкните Проверьте последние** определения вирусов и программ-шпионов при запуске и установите параметр **Включено**. 

6. Нажмите кнопку **ОК**.

Вы также можете использовать групповую политику, PowerShell или WMI для настройки антивируса Microsoft Defender для проверки обновлений при запуске, даже если он не запущен.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Используйте групповую политику для скачивания обновлений, когда антивирус Microsoft Defender не присутствует

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **Политики,** а **затем административные шаблоны**.

4. Расширь дерево до **компонентов Microsoft**  >  **Defender Antivirus** Security Intelligence  >  **Updates**.

5. Дважды **щелкните Инициировать обновление** сведении о безопасности при запуске и установите параметр **Включено.**

6. Нажмите кнопку **ОК**.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Используйте cmdlets PowerShell для скачивания обновлений при неявке антивируса Microsoft Defender

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

Дополнительные сведения см. в [cmdlets Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) для управления антивирусными и защитниками Microsoft Defender, чтобы получить дополнительные сведения о том, как использовать PowerShell с антивирусом Microsoft Defender. [](/powershell/module/defender/index)

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Используйте инструкцию по управлению Windows (WMI) для скачивания обновлений, когда антивирус Microsoft Defender не присутствует

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

Дополнительные сведения см. [в Защитник Windows API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>Разрешить ad hoc changes to protection based on cloud-delivered protection

Microsoft Defender AV может вносить изменения в свою защиту на основе облачной защиты. Такие изменения могут происходить вне обычных или запланированных обновлений защиты.

Если у вас включена облачная защита, microsoft Defender AV отправляет файлы, подозрительные для Защитник Windows облака. Если облачная служба сообщает о том, что файл вредоносный, а файл обнаружен в недавнем обновлении защиты, можно использовать групповую политику для настройки microsoft Defender AV для автоматического получения этого обновления защиты. Также можно применить другие важные обновления защиты.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>Использование групповой политики для автоматической загрузки последних обновлений на основе облачной защиты

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **Политики,** а **затем административные шаблоны**.

4. Расширь дерево до **компонентов Microsoft**  >  **Defender Antivirus** Security Intelligence  >  **Updates**.

5. Дважды **щелкните Разрешить обновления** сведении о безопасности в режиме реального времени на основе отчетов в Microsoft MAPS и установите параметр **Включено**. Нажмите кнопку **ОК**.

6. **Разрешить уведомления для отключения отчетов** на основе определений в Microsoft MAPS и установить параметр **Включено**. Нажмите кнопку **ОК**.
    
> [!NOTE]
> **Разрешение уведомлений для отключения** отчетов на основе определений позволяет Microsoft MAPS отключить эти определения, которые, как известно, вызывают ложные сообщения. Для работы этой функции необходимо настроить компьютер, чтобы присоединиться к Microsoft MAPS.

## <a name="see-also"></a>См. также

- [Развертывание антивируса Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Управление обновлениями антивируса Microsoft Defender и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Управление загрузкой и приложением обновлений защиты](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Управление обновлениями для мобильных устройств и виртуальных машин (виртуальных машин)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)