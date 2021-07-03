---
title: Управление Microsoft Defender для конечной точки с помощью PowerShell, WMI и MPCmdRun.exe
description: Узнайте, как управлять Microsoft Defender для конечной точки с помощью PowerShell, WMI и MPCmdRun.exe
keywords: после миграции, управления, операций, обслуживания, использования, PowerShell, WMI, MPCmdRun.exe, Microsoft Defender для endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 063870c58377d7327f621ec49855b684065f436b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286769"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Управление Microsoft Defender для конечной точки с помощью PowerShell, WMI и MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Рекомендуется использовать [Microsoft Endpoint Manager](/mem) для управления функциями защиты от угроз для устройств (также именуемой конечными точками). Endpoint Manager [включает](/mem/intune/fundamentals/what-is-intune) Microsoft Intune [и Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction).
>
> - [Дополнительные дополнительные Endpoint Manager](/mem/endpoint-manager-overview)
> - [Совместное управление Microsoft Defender для конечной точки на Windows 10 устройствах с помощью Configuration Manager и Intune](manage-atp-post-migration-intune.md)
> - [Управление microsoft Defender для конечной точки с помощью Intune](manage-atp-post-migration-intune.md)

Вы можете управлять некоторыми антивирусная программа в Microsoft Defender на устройствах с [помощью PowerShell,](#configure-microsoft-defender-for-endpoint-with-powershell) [Windows](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) инструментов управления (WMI) и командной строки microsoft [Malware Protection](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe). Например, вы можете управлять некоторыми антивирусная программа в Microsoft Defender параметров. В некоторых случаях можно настроить правила уменьшения поверхности атаки и использовать параметры защиты.

> [!IMPORTANT]
> Функции защиты от угроз, настроенные с помощью PowerShell, WMI или MCPmdRun.exe, можно перезаписать с помощью параметров конфигурации, развернутых с помощью Intune или Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Настройка Microsoft Defender для конечной точки с помощью PowerShell

Вы можете использовать PowerShell для управления антивирусная программа в Microsoft Defender, защиты от эксплуатации и правил уменьшения поверхности атаки.

|Задача|Дополнительные ресурсы|
|---|---|
|**Управление антивирусная программа в Microsoft Defender** <p> Просмотр состояния защиты от антивирусных программ, настройка предпочтений для & обновлений и внесение других изменений в антивирусную защиту.*|[Для настройки и управления антивирусная программа в Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus) <p> [Использование cmdlets PowerShell для обеспечения облачной защиты](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)|
|**Настройка защиты от эксплойтов** для смягчения угроз на устройствах организации <p> *Рекомендуется сначала использовать защиту от [эксплойтов в режиме](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) аудита. Таким образом можно увидеть, как защита от эксплойтов влияет на приложения, которые использует ваша организация.*|[Настройка защиты от эксплойтов](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <p> [Cmdlets PowerShell для защиты от эксплойтов](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)|
|**Настройка правил уменьшения поверхности атаки** с помощью PowerShell <p> *Вы можете использовать PowerShell, чтобы исключить файлы и папки из правил уменьшения поверхности атаки.*|[Настройка правил уменьшения поверхности атаки: использование PowerShell для исключения файлов & папок](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders) <p> Кроме того, см. в графическом средстве пользовательского интерфейса [António Vasconcelo](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)для установки правил уменьшения поверхности атаки с помощью PowerShell.|
|**Включить защиту сети** с помощью PowerShell <p> *Вы можете использовать PowerShell для обеспечения сетевой защиты.*|[Включив защиту сети с помощью PowerShell](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell)|
|**Настройка управляемого доступа к папкам для** защиты от программ-вымогателей <p> *[Управляемый доступ к папкам](/microsoft-365/security/defender-endpoint/controlled-folders) также называется защитой от антивирусных программ.*|[Включить управляемый доступ к папкам с помощью PowerShell](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell)|
|**Настройка брандмауэра Microsoft Defender,** чтобы блокировать несанкционированный сетевой трафик, который втекает на устройства организации или выходит из нее.|[Брандмауэр Microsoft Defender с расширенным администрированием безопасности с Windows PowerShell](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell)|
|**Настройка шифрования и BitLocker для** защиты информации на устройствах организации, работающих Windows|[Справочный справочник BitLocker PowerShell](/powershell/module/bitlocker/)|

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Настройка Microsoft Defender для конечной точки с помощью Windows управления (WMI)

WMI — это интерфейс скриптов, который позволяет извлекать, изменять и обновлять параметры. Дополнительные дополнительные информации см. [в см. в этой ленте Using WMI.](/windows/win32/wmisdk/using-wmi)

|Задача|Дополнительные ресурсы|
|---|---|
|**Включить облачную защиту** на устройстве|[Использование Windows управления (WMI) для обеспечения облачной защиты](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)|
|**Извлечение, изменение** и обновление параметров для антивирусная программа в Microsoft Defender|[Использование WMI для настройки и управления антивирусная программа в Microsoft Defender] (/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus <p> [Просмотрите список доступных классов WMI и сценариев примера](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <p> Также см. архивные [Защитник Windows WMIv2 Provider](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)|

## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Настройка Microsoft Defender для конечной точки с помощью microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

На отдельном устройстве можно выполнить сканирование, начать диагностику, проверить обновления сведений о безопасности и другие сведения с помощью средства mpcmdrun.exe командной строки. Вы можете найти утилиту `%ProgramFiles%\Windows Defender\MpCmdRun.exe` в . Запустите его из командной подсказки.

|Задача|Дополнительные ресурсы|
|---|---|
|**Управление антивирусная программа в Microsoft Defender**|[Настройка и управление антивирусная программа в Microsoft Defender с mpcmdrun.exe](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)|

## <a name="configure-your-microsoft-defender-security-center"></a>Настройка Центр безопасности в Microsoft Defender

Если вы еще этого не сделали, настройте Центр безопасности в Microsoft Defender **()** для просмотра оповещений, настройки функций защиты от угроз и просмотра подробных сведений об общей позиции безопасности [https://securitycenter.windows.com](https://securitycenter.windows.com) организации.

Вы также можете настроить, можно ли и какие функции конечные пользователи могут видеть в Центр безопасности в Microsoft Defender.

- [Обзор Центр безопасности в Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Защита конечных точек: Центр безопасности в Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Дальнейшие действия

- [Обзор контроля угроз и уязвимостей](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Посетите панель мониторинга Центр безопасности в Microsoft Defender операций безопасности](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Управление microsoft Defender для конечной точки с помощью Intune](manage-atp-post-migration-intune.md)
