---
title: Настройка исправления для обнаружения антивирусной программы в Microsoft Defender
description: Настройка того, антивирусная программа в Microsoft Defender следует делать при обнаружении угрозы, и как долго должны храниться карантинные файлы в папке карантина
keywords: исправление, исправление, удаление, угрозы, карантин, сканирование, восстановление
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9b765d14e31d6c4890aeace41e4fe79bafdd889e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925579"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Настройка исправления для обнаружения антивирусной программы в Microsoft Defender


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Когда антивирусная программа в Microsoft Defender выполняется проверка, она пытается устранить обнаруженные угрозы или устранить их. Можно настроить, антивирусная программа в Microsoft Defender должны быть устранены определенные угрозы, должна ли быть создана точка восстановления перед исправлением и когда угрозы должны быть удалены.

В этой статье описывается настройка этих параметров с помощью групповой политики, но вы также можете использовать Microsoft Endpoint Configuration Manager [и Microsoft Intune](/intune/device-restrictions-configure). [](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) 

Для настройки этих параметров можно также использовать класс [ `Set-MpPreference` PowerShell](/powershell/module/defender/set-mppreference) или [ `MSFT_MpPreference` WMI.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="configure-remediation-options"></a>Настройка параметров восстановления

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**

3. Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**. 

4. Используя приведенную ниже таблицу, выберите расположение и по мере необходимости отредактировать политику. 

5. Нажмите **ОК**.

|Местоположение | Setting | Описание | Параметр по умолчанию (если не настроен) |
|:---|:---|:---|:---|
|Проверка | Создание точки восстановления системы | Каждый день перед попыткой очистки или сканирования будет создана точка восстановления системы | Отключено|
|Проверка | Включаем удаление элементов из папки истории сканирования | Укажите, сколько дней элементов должно храниться в истории сканирования | 30 дней |
|Root | Отключение плановых исправлений | Можно указать, антивирусная программа в Microsoft Defender автоматически устраняет угрозы, или следует задать пользователю конечной точки, что делать. | Отключено (угрозы устраняются автоматически) |
|Карантин | Настройка удаления элементов из папки Карантина | Укажите, сколько дней необходимо хранить в карантине перед удалением | 90 дней |
|Threats | Укажите уровни оповещений об угрозах, на которых по умолчанию не следует принимать меры при обнаружении | Каждой угрозе, обнаруженной антивирусная программа в Microsoft Defender, назначен уровень угрозы (низкий, средний, высокий или серьезный). Этот параметр можно использовать для определения того, как следует устранять все угрозы для каждого из уровней угроз (карантин, удаление или игнорирование) | Неприменимо |
|Threats | Укажите угрозы, при которых по умолчанию не следует принимать меры при обнаружении | Укажите, как следует устранять определенные угрозы (используя их ID угрозы). Можно указать, должна ли конкретная угроза быть карантином, удалена или проигнорирована | Неприменимо |

> [!IMPORTANT]
> антивирусная программа в Microsoft Defender обнаруживает и устраняет файлы, основанные на многих факторах. Иногда для выполнения исправлений требуется перезагрузка. Даже если позднее будет установлено, что обнаружение является ложным срабатывательством, перезагрузка должна быть завершена, чтобы убедиться, что все дополнительные действия по исправлению завершены.
>
> Если вы уверены, антивирусная программа в Microsoft Defender на карантин файл на основе ложного срабатыва, вы можете восстановить файл из карантина после перезагрузки устройства. Подробнее [о восстановлении карантинов в антивирусная программа в Microsoft Defender.](restore-quarantined-files-microsoft-defender-antivirus.md)
> 
> Чтобы избежать этой проблемы в будущем, можно исключить файлы из сканов. См. в рубке Настройка и проверка исключений [для антивирусная программа в Microsoft Defender проверки.](configure-exclusions-microsoft-defender-antivirus.md)

Также [см. в](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) рубке Настройка необходимых для восстановления запланированных антивирусная программа в Microsoft Defender для дополнительных параметров, связанных с исправлением.

## <a name="see-also"></a>См. также

- [Настройка параметров сканирования антивирусной программы в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Настройка запланированных антивирусная программа в Microsoft Defender сканирования](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Настройка и запуск проверки антивирусной программой в Microsoft Defender по требованию](run-scan-microsoft-defender-antivirus.md).
- [Настройка уведомлений, отображающихся в конечных точках](configure-notifications-microsoft-defender-antivirus.md)
- [Настройка взаимодействия между конечными антивирусная программа в Microsoft Defender пользователями](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Настройка, инициирование и проверка результатов антивирусная программа в Microsoft Defender и исправлений](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
