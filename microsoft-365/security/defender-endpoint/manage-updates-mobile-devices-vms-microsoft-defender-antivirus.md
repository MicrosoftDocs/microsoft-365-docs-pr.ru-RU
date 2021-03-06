---
title: Определите, как мобильные устройства обновляются антивирусная программа в Microsoft Defender
description: Управление обновлением мобильных устройств, таких как ноутбуки, с помощью антивирусная программа в Microsoft Defender обновлений защиты.
keywords: обновления, защита, обновления расписания, батареи, мобильного устройства, ноутбука, ноутбука, выбора, обновления Майкрософт, wsus, переопределения
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 809f4573c91f7f1882693cbd8c63d88b06b55c67
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926011"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Мобильным устройствам и VM-устройствам может потребоваться больше конфигурации для обеспечения того, чтобы на производительность не повлияли обновления.

Существует два параметра, которые полезны для этих устройств:

- В приложении Microsoft Update на мобильных компьютерах без подключения wSUS
- Предотвращение обновлений сведении о безопасности при работе с питанием от батареи

В таких ситуациях также могут быть полезны следующие статьи:
- [Настройка запланированных и доголовных сканов](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Руководство по развертыванию антивирусной программы в Microsoft Defender в среде инфраструктуры виртуальных рабочих столов (VDI)](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>В приложении Microsoft Update на мобильных компьютерах без подключения wSUS

С помощью Microsoft Update можно сохранить сведения о безопасности на мобильных устройствах, работающих антивирусная программа в Microsoft Defender, если они не подключены к корпоративной сети или не подключены к WSUS. 

Это означает, что обновления защиты можно доставить на устройства (через Microsoft Update), даже если вы задали WSUS переопределение обновления Microsoft.

Вы можете выбрать microsoft Update на мобильном устройстве одним из следующих способов:

- Измените параметр с помощью групповой политики.
- Чтобы создать скрипт, используйте VBScript, а затем запустите его на каждом компьютере в сети.
- Вручную выберите каждый компьютер в сети через **Параметры** меню.

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Использование групповой политики для выбора обновления Майкрософт

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Выберите **политики,** а затем **административные шаблоны**.

4. Расширь **дерево до Windows компонентов**  >  **антивирусная программа в Microsoft Defender**  >  **обновлений подписи.**

5. Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select **OK.**


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Используйте VBScript для выбора в Microsoft Update

1. Используйте инструкции в статье MSDN [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) для создания VBScript.

2. Запустите VBScript, созданный на каждом компьютере в сети.

### <a name="manually-opt-in-to-microsoft-update"></a>Вручную войти в Microsoft Update

1. Откройте **Windows в** **обновлении &** параметры безопасности на компьютере, в который вы хотите войти.

2. Выберите **расширенные** параметры.

3. Выберите почтовый ящик **для Give me updates for other Microsoft products when I update Windows.**

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Предотвращение обновлений сведении о безопасности при работе с питанием от батареи

Вы можете настроить антивирусная программа в Microsoft Defender только для скачивания обновлений защиты, когда компьютер подключен к проводной источник питания. 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Использование групповой политики для предотвращения обновлений сведений о безопасности на заряде батареи

1.  На компьютере управления групповой [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))политикой откройте консоль управления групповой политикой, выберите объект групповой политики, который необходимо настроить, и откройте его для редактирования.

2.  В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

3.  Выберите **политики,** а затем **административные шаблоны**.

4.  Развяжите дерево до **Windows компонентов**  >  **антивирусная программа в Microsoft Defender**  >  **обновлений** подписей,  а затем установите разрешить обновления сведении безопасности при работе с отключенным питанием от **батареи.** После этого нажмите кнопку **ОК**. 

Это действие предотвращает загрузку обновлений защиты при подзаряжаемом компьютере.

## <a name="related-articles"></a>Связанные статьи

- [Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Обновление и управление антивирусная программа в Microsoft Defender в Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)