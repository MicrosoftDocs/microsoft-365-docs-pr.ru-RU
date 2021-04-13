---
title: Настройка исправлений для обнаружения антивируса Microsoft Defender
description: Настройка того, что должен делать антивирус Microsoft Defender при обнаружении угрозы, и как долго должны храниться карантинные файлы в папке карантина
keywords: исправление, исправление, удаление, угрозы, карантин, сканирование, восстановление
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f41e9c5b38e93ce84fbd971e02ebc2d77432c3f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690859"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Настройка исправлений для обнаружения антивируса Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Когда антивирус Microsoft Defender выполняет проверку, он пытается устранить обнаруженные угрозы или устранить их. Можно настроить, как антивирус Microsoft Defender должен устранять определенные угрозы, следует ли создавать точку восстановления перед исправлением и когда угрозы должны быть удалены.

В этой статье описывается настройка этих параметров с помощью групповой политики, но вы также можете использовать [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) и Microsoft [Intune.](/intune/device-restrictions-configure) 

Для настройки этих параметров можно также использовать класс [ `Set-MpPreference` PowerShell](/powershell/module/defender/set-mppreference) или [ `MSFT_MpPreference` WMI.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="configure-remediation-options"></a>Настройка параметров восстановления

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**

3. Расширь дерево до **компонентов Microsoft**  >  **Defender Antivirus**. 

4. Используя приведенную ниже таблицу, выберите расположение и по мере необходимости отредактировать политику. 

5. Нажмите кнопку **ОК**.

|Расположение | Setting | Описание | Параметр по умолчанию (если не настроен) |
|:---|:---|:---|:---|
|Проверка | Создание точки восстановления системы | Каждый день перед попыткой очистки или сканирования будет создана точка восстановления системы | Отключена|
|Проверка | Включаем удаление элементов из папки истории сканирования | Укажите, сколько дней элементов должно храниться в истории сканирования | 30 дней |
|Root | Отключение плановых исправлений | Вы можете указать, устраняет ли антивирус Microsoft Defender автоматически угрозы или должен ли он задать пользователю конечной точки, что делать. | Отключено (угрозы устраняются автоматически) |
|Карантин | Настройка удаления элементов из папки Карантина | Укажите, сколько дней необходимо хранить в карантине перед удалением | 90 дней |
|Threats | Укажите уровни оповещений об угрозах, на которых по умолчанию не следует принимать меры при обнаружении | Каждой угрозе, обнаруженной антивирусом Microsoft Defender, назначен уровень угрозы (низкий, средний, высокий или серьезный). Этот параметр можно использовать для определения того, как следует устранять все угрозы для каждого из уровней угроз (карантин, удаление или игнорирование) | Неприменимо |
|Threats | Укажите угрозы, при которых по умолчанию не следует принимать меры при обнаружении | Укажите, как следует устранять определенные угрозы (используя их ID угрозы). Можно указать, должна ли конкретная угроза быть карантином, удалена или проигнорирована | Неприменимо |

> [!IMPORTANT]
> Антивирус Microsoft Defender обнаруживает и устраняет файлы, основанные на многих факторах. Иногда для выполнения исправлений требуется перезагрузка. Даже если позднее будет установлено, что обнаружение является ложным срабатывательством, перезагрузка должна быть завершена, чтобы убедиться, что все дополнительные действия по исправлению завершены.
>
> Если вы уверены, что антивирус Microsoft Defender карантин для файла основан на ложном срабатывке, вы можете восстановить файл из карантина после перезагрузки устройства. Подробнее [о восстановлении карантиных файлов см. в антивирусе Microsoft Defender.](restore-quarantined-files-microsoft-defender-antivirus.md)
> 
> Чтобы избежать этой проблемы в будущем, можно исключить файлы из сканов. См. [в рубке Настройка и проверка исключений для проверки антивирусных программ Microsoft Defender.](configure-exclusions-microsoft-defender-antivirus.md)

Кроме [того, см.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) в этой ссылке Настройка запланированных полных антивирусных сканов Microsoft Defender для дополнительных параметров, связанных с исправлением.

## <a name="see-also"></a>См. также

- [Настройка параметров антивирусного сканирования Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Настройка запланированных антивирусных сканов Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Настройка и запуск антивирусных сканов Microsoft Defender по запросу](run-scan-microsoft-defender-antivirus.md)
- [Настройка уведомлений, которые отображаются в конечных точках](configure-notifications-microsoft-defender-antivirus.md)
- [Настройка взаимодействия антивируса Microsoft Defender с конечным пользователем](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Настройка, инициирование и проверка результатов проверки и устранения антивирусных программ Microsoft Defender](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)