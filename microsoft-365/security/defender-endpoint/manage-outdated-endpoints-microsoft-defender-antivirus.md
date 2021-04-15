---
title: Применение обновлений av-защиты Защитника Майкрософт к конечным точкам устарели
description: Определите, когда и как следует применять обновления для конечных точек, которые не обновлялись некоторое время.
keywords: обновления, защита, устаревшие, устаревшие, старые, догонять
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 81c7fb2bb7cd20fea3f343097811078ed744c3eb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765375"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Управление обновлениями и проверками устаревших конечных точек антивирусной программы в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Антивирус Microsoft Defender позволяет определить, как долго конечная точка может избежать обновления или сколько сканов она может пропустить, прежде чем потребуется обновить и сканировать себя. Это особенно полезно в средах, где устройства не часто подключены к корпоративной или внешней сети, или устройства, которые не используются ежедневно.

Например, сотрудник, использующий определенный компьютер, находится в перерыве в течение трех дней и не входит на свой компьютер в течение этого времени.

Когда пользователь вернется к работе и войдите на свой компьютер, антивирус Microsoft Defender немедленно проверит и загрузит последние обновления защиты и запустит сканирование.

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>Настройка обновлений защиты для конечных точек, которые не обновлялись некоторое время

Если антивирус Microsoft Defender не скачал обновления защиты за указанный период, его можно настроить для автоматической проверки и скачивания последнего обновления в следующем журнале. Это полезно, если во всем мире отключены автоматические загрузки обновлений [при запуске.](manage-event-based-updates-microsoft-defender-antivirus.md)

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Использование Диспетчер конфигурации для настройки обновлений защиты догонять

1.  На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ, которые необходимо изменить (нажмите кнопку Активы и соответствие требованиям в области навигации слева, а затем расширите дерево до Обзор политики защиты конечных   >    >  точек)

2.  Перейдите в **раздел Обновления** сведении безопасности и настройте следующие параметры:

    1. Установите **force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.
    2. Для  **if Configuration Manager** используется в качестве источника обновления сведении о безопасности... Укажите часы, до которых обновления защиты, доставленные диспетчером конфигурации, должны считаться устарели. Это приведет к следующему расположению обновления, основанному на определенном порядке источника [отката.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)

3. Нажмите кнопку **ОК**.

4.  [Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>Используйте групповую политику, чтобы включить и настроить функцию догонять обновление

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **Политики,** а **затем административные шаблоны**.

4. Расширь дерево до **компонентов Windows > антивируса Microsoft Defender > обновлений подписи**.

5. Дважды щелкните **определение** числа дней, после которых требуется настройка догонять обновление сведении о безопасности, и установите параметр **Включено**. Введите количество дней, после которых вы хотите, чтобы microsoft Defender AV проверил и скачал последнее обновление защиты.

6. Нажмите кнопку **ОК**.

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>Используйте cmdlets PowerShell для настройки обновлений защиты наверстать упущенное

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)  с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Используйте инструкцию по управлению Windows (WMI) для настройки обновлений защиты догонять

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
SignatureUpdateCatchupInterval
```

Дополнительные сведения и допустимые параметры см. в следующих сведениях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>Установите количество дней до того, как защита будет отчитаться о том, что она устарела

Вы также можете указать количество дней, после которых антивирусная защита Microsoft Defender считается старой или устарелой. После указанного числа дней клиент будет сообщать о себе как о устарелом состоянии и показывать ошибку пользователю компьютера. Это также может вызвать попытку загрузки антивируса Microsoft Defender из других [](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)источников (на основе определенного источника отката), например при использовании MMPC в качестве дополнительного источника после установки WSUS или Microsoft Update в качестве первого источника.

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>Используйте групповую политику, чтобы указать количество дней до того, как защита будет считаться устарелой

1.  На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

3.  В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

4.  Щелкните **Политики,** а **затем административные шаблоны**.

5.  Расширь дерево до компонентов **Windows > антивируса Microsoft Defender >** обновления подписей и настройте следующие параметры:

    1.  Дважды **щелкните Определить количество** дней до того, как определения программ-шпионов будут считаться устарели, и установите параметр **Включен**. Введите количество дней, после которых microsoft Defender AV считает данные службы безопасности шпионских программ устарели.

    2. Нажмите кнопку **ОК**.

    3.  Дважды **щелкните Определить количество дней до** того, как определения вирусов будут считаться устарели, и установите параметр **Включено**. Введите количество дней, после которых microsoft Defender AV считает данные службы безопасности вирусов устарели.

    4. Нажмите кнопку **ОК**.


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>Настройка доголовных сканов для конечных точек, которые не были сканированы некоторое время

Вы можете установить количество последовательных запланированных сканов, которые можно пропустить до того, как антивирус Microsoft Defender принудит к проверке.

Процесс включения этой функции:

1. Настройка по крайней мере одного запланированного сканирования (см. раздел [Проверка расписания).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
2. Включить функцию догонять сканирование.
3. Определите количество сканов, которые можно пропустить до начала проверки.

Эта функция может быть включена как для полного, так и для быстрого сканирования.

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>Использование групповой политики, чтобы включить и настроить функцию догонять сканирование

1.  Убедитесь, что вы настроили хотя бы одно запланированное сканирование.

2.  На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

3.  В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

4.  Щелкните **Политики,** а **затем административные шаблоны**.

5.  Расширь дерево до **компонентов Windows > антивируса Microsoft Defender >** сканирование и настройте следующие параметры:

    1.  Если вы настроили запланированные быстрые проверки, дважды нажмите кнопку Включить параметр быстрого сканирования и установите параметр **Включено**.  
    2. Если вы настроили запланированные полные проверки, дважды щелкните параметр **Turn on catch-up full scan** и установите параметр **Включено**. Нажмите кнопку **ОК**.
    3. Дважды щелкните **кнопку Определить количество** дней, после которых принудительный параметр проверки наверстать упущенное, и установите параметр **Включено.** 
    4. Введите число сканов, которые можно пропустить перед автоматическим запуском сканирования при следующем входе пользователя на компьютер. Тип сканирования, который будет запускаться, определяется типом проверки, который необходимо использовать для запланированного сканирования **(см.** раздел Расписание [сканирования).](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Нажмите кнопку **ОК**.

> [!NOTE]
> Заголовок параметра групповой политики относится к числу дней. Однако этот параметр применяется к числу сканов (не дней) перед запуском догонять.

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>Для настройки догоняемых сканов используйте cmdlets PowerShell

Используйте следующие cmdlets:

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)  с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Использование инструкции по управлению Windows (WMI) для настройки доголовных сканов

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

Дополнительные сведения и допустимые параметры см. в следующих сведениях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Настройка доголовных сканов с помощью диспетчера конфигурации

1.  На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ, которые необходимо изменить (нажмите кнопку Активы и соответствие требованиям в области навигации слева, а затем расширите дерево до Обзор политики защиты конечных   >    >  точек)

2.  Перейдите в раздел **Запланированные** проверки и привяжье сканирование выбранного типа сканирования, если клиентский компьютер находится в автономном **режиме...** 

3. Нажмите кнопку **ОК**.

4.  [Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="related-articles"></a>Статьи по теме

- [Развертывание антивируса Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Управление обновлениями антивируса Microsoft Defender и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Управление загрузкой и приложением обновлений защиты](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Управление принудительными обновлениями на основе событий](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)