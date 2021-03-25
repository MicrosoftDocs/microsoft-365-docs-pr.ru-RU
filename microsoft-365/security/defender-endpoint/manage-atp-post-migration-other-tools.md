---
title: Управление Microsoft Defender для конечной точки с помощью PowerShell, WMI и MPCmdRun.exe
description: Узнайте, как управлять Microsoft Defender для конечной точки с помощью PowerShell, WMI и MPCmdRun.exe
keywords: после миграции, управления, операций, обслуживания, использования, PowerShell, WMI, MPCmdRun.exe, защита от угроз защитника Windows, atp, edr
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
ms.openlocfilehash: 5f0e94360cfaa0c66aedec400e81adc85f4f5450
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185877"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Управление Microsoft Defender для конечной точки с помощью PowerShell, WMI и MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Мы рекомендуем использовать [Microsoft Endpoint Manager](https://docs.microsoft.com/mem) для управления функциями защиты от угроз для устройств (также именуемой конечными точками). Endpoint Manager включает [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) и [Microsoft Endpoint Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) 
> - [Дополнительные дополнительные информацию о диспетчере конечных точек](https://docs.microsoft.com/mem/endpoint-manager-overview)
> - [Совместное управление Microsoft Defender для конечной точки на устройствах Windows 10 с помощью configuration Manager и Intune](manage-atp-post-migration-intune.md)
> - [Управление microsoft Defender для конечной точки с помощью Intune](manage-atp-post-migration-intune.md) 

Вы можете управлять некоторыми антивирусными настройками Microsoft Defender на устройствах [с powerShell,](#configure-microsoft-defender-for-endpoint-with-powershell) [инструментами](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) управления Windows (WMI) и командной строкой microsoft [Malware Protection (MPCmdRun.exe).](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) Например, можно управлять некоторыми антивирусными настройками Microsoft Defender. В некоторых случаях можно настроить правила уменьшения поверхности атаки и использовать параметры защиты. 

> [!IMPORTANT]
> Функции защиты от угроз, настроенные с помощью PowerShell, WMI или MCPmdRun.exe, можно перезаписать с помощью параметров конфигурации, развернутых с помощью Intune или Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Настройка Microsoft Defender для конечной точки с помощью PowerShell

С помощью PowerShell можно управлять антивирусом Microsoft Defender, использовать защиту и правила уменьшения поверхности атак.

|Задача  |Дополнительные ресурсы  |
|---------|---------|
|**Управление антивирусной программой Microsoft Defender** <br/><br/>*Просмотр состояния защиты от антивирусных программ, настройка предпочтений для & обновлений и внесение других изменений в антивирусную защиту.*    |[Используйте cmdlets PowerShell для настройки и управления антивирусом Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[Использование cmdlets PowerShell для обеспечения облачной защиты](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**Настройка защиты от эксплойтов** для смягчения угроз на устройствах организации<br/><br/> *Рекомендуется сначала использовать защиту от [эксплойтов в режиме](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) аудита. Таким образом можно увидеть, как защита от эксплойтов влияет на приложения, которые использует ваша организация.*     | [Настройка защиты от эксплойтов](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[Cmdlets PowerShell для защиты от эксплойтов](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|**Настройка правил уменьшения поверхности атаки** с помощью PowerShell <br/><br/>*Вы можете использовать PowerShell, чтобы исключить файлы и папки из правил уменьшения поверхности атаки.* |[Настройка правил уменьшения поверхности атаки: использование PowerShell для исключения файлов & папок](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>Кроме того, см. в графическом средстве пользовательского интерфейса [António Vasconcelo](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)для установки правил уменьшения поверхности атаки с помощью PowerShell. |
|**Включить защиту сети** с помощью PowerShell <br/><br/>*Вы можете использовать PowerShell для обеспечения сетевой защиты.* |[Включив защиту сети с помощью PowerShell](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**Настройка управляемого доступа к папкам для** защиты от программ-вымогателей <br/><br/>*[Управляемый доступ к папкам](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) также называется защитой от антивирусных программ.* |[Включить управляемый доступ к папкам с помощью PowerShell](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**Настройка брандмауэра Microsoft Defender,** чтобы блокировать несанкционированный сетевой трафик, который втекает на устройства организации или выходит из нее. |[Брандмауэр Microsoft Defender с расширенным администрированием безопасности с Windows PowerShell](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|**Настройка шифрования и BitLocker для** защиты информации на устройствах организации под управлением Windows |[Справочный справочник BitLocker PowerShell](https://docs.microsoft.com/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Настройка Microsoft Defender для конечной точки с помощью инструментов управления Windows (WMI)

WMI — это интерфейс скриптов, который позволяет извлекать, изменять и обновлять параметры. Дополнительные дополнительные информации см. [в см. в этой ленте Using WMI.](https://docs.microsoft.com/windows/win32/wmisdk/using-wmi) 

|Задача  |Дополнительные ресурсы  |
|---------|---------|
|**Включить облачную защиту** на устройстве    |[Использование инструкции по управлению Windows (WMI) для обеспечения облачной защиты](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|**Извлечение, изменение и обновление параметров** антивируса Microsoft Defender     | [Использование WMI для настройки и управления антивирусом Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[Просмотрите список доступных классов WMI и сценариев примера](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>Также см. архивные [Защитник Windows WMIv2 Provider](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Настройка Microsoft Defender для конечной точки с помощью microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

На отдельном устройстве можно выполнить сканирование, начать диагностику, проверить обновления сведений о безопасности и другие сведения с помощью средства mpcmdrun.exe командной строки. Вы можете найти утилиту `%ProgramFiles%\Windows Defender\MpCmdRun.exe` в . Запустите его из командной подсказки.

|Задача  |Дополнительные ресурсы  |
|---------|---------|
|**Управление антивирусной программой Microsoft Defender**  |[Настройка и управление антивирусом Microsoft Defender с помощью mpcmdrun.exe](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>Настройка центра безопасности Microsoft Defender

Если вы еще этого не сделали, настройте центр безопасности **Microsoft Defender** Для просмотра оповещений, настройки функций защиты от угроз и просмотра подробных сведений об общей позиции безопасности [https://securitycenter.windows.com](https://securitycenter.windows.com) организации. 

Вы также можете настроить, можно ли и какие функции конечные пользователи могут видеть в Центре безопасности Microsoft Defender.

- [Обзор Центра безопасности Защитника Майкрософт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Защита конечной точки: Центр безопасности Защитника Майкрософт](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>Дальнейшие действия

- [Обзор управления угрозами и уязвимостью](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Посетите панель мониторинга операций безопасности Центра безопасности Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Управление microsoft Defender для конечной точки с помощью Intune](manage-atp-post-migration-intune.md)
