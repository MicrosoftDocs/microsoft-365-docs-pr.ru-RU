---
title: Расписание антивирусная программа в Microsoft Defender обновлений защиты
description: Расписание дня, времени и интервала для загрузки обновлений защиты
keywords: обновления, базовые показатели безопасности, расписание обновлений
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 26b88b8677c27a5d6615776a371326e37034afd4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275040"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Управление расписанием загрузки и применения обновлений защиты

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

антивирусная программа в Microsoft Defender позволяет определить, когда следует искать и загружать обновления.

Вы можете запланировать обновления для конечных точек по: 

- Указание дня недели для проверки обновлений защиты 
- Указание интервала для проверки обновлений защиты
- Указание времени проверки обновлений защиты

Вы также можете рандомизировать время, когда каждая конечная точка проверяет и скачивает обновления защиты. Дополнительные [сведения см. в](scheduled-catch-up-scans-microsoft-defender-antivirus.md) разделе Проверка расписания.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Использование диспетчера конфигурации для расписания обновлений защиты

1.  На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ,  которые необходимо изменить (щелкните Активы и соответствие требованиям в области навигации слева, а затем разогнайте дерево до Endpoint Protection  >    >  **antimalware Policies**)

2.  Перейдите в **раздел Обновления сведении безопасности.**

3. Проверка и загрузка обновлений в определенное время:
      1. Установите проверку Endpoint Protection обновлений разведки безопасности **с определенным интервалом...** до **0**.
      2. Установите проверку Endpoint Protection обновлений разведки безопасности ежедневно **по времени проверки** обновлений.
      3
4. Для проверки и загрузки обновлений на непрерывном интервале установите Endpoint Protection обновления сведении безопасности за определенный **интервал...** до количества часов, которые должны происходить между обновлениями.

5.  [Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="use-group-policy-to-schedule-protection-updates"></a>Использование групповой политики для расписания обновлений защиты

> [!IMPORTANT]
> По умолчанию антивирусная программа в Microsoft Defender будет проверять обновление за 15 минут до времени запланированного сканирования. Включение этих параметров переопределит этот по умолчанию.

1.  На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

3.  В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

4.  Щелкните **Политики,** а **затем административные шаблоны**.

5.  Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **signature Intelligence Updates** и настройте следующие параметры:

    1. Дважды нажмите кнопку **Укажите** день недели, чтобы проверить параметр обновления сведении безопасности и задать параметр **Включено**. Введите день недели, чтобы проверить обновления. Нажмите кнопку **ОК**.
    2. Дважды нажмите кнопку **Укажите интервал для проверки** параметров обновлений разведки безопасности и установите параметр **Включено.** Введите количество часов между обновлениями. Нажмите кнопку **ОК**.
    3. Дважды щелкните **кнопку Укажите время** для проверки параметра обновлений разведки безопасности и установите параметр **Включено.** Введите время проверки обновлений. Время основано на локальном времени конечной точки. Нажмите кнопку **ОК**.


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>Использование cmdlets PowerShell для расписания обновлений защиты

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

Дополнительные сведения о том, как использовать [PowerS антивирусная программа в Microsoft Defender hell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусная программа в Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Используйте Windows управления (WMI) для расписания обновлений защиты

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Дополнительные сведения и допустимые параметры см. в следующих сведениях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Статьи по теме

- [Развертывание антивирусная программа в Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Управление принудительными обновлениями на основе событий](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [антивирусная программа в Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)