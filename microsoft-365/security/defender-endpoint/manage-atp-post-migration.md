---
title: Управление миграцией столба в конечной точке в Microsoft Defender для конечной точки
description: Теперь, когда вы перешли на Microsoft Defender для конечной точки, следующим шагом будет управление функциями защиты от угроз.
keywords: после переноса, управления, операций, обслуживания, использования, Microsoft Defender для конечной точки, edr
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
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: ea5e4cb1c4a93f5f8bd5da1c0c94b095d03ac680
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845622"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Управление защитником Майкрософт для конечной точки, после переноса

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

После того как вы перешли от предыдущего решения по защите конечной точки и антивирусу к Microsoft Defender для конечной точки, следующим шагом будет управление своими функциями и возможностями. Рекомендуется использовать [Microsoft Endpoint Manager,](/mem/endpoint-manager-overview)Microsoft Intune и [](/mem/intune/fundamentals/what-is-intune) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/core/understand/introduction)для управления устройствами и настройками безопасности организации. Однако вы можете использовать другие средства и методы, например объекты групповой политики [в Azure Active Directory служб домена.](/azure/active-directory-domain-services/manage-group-policy) 

В следующей таблице перечислены различные инструменты и методы, которые можно использовать, а также ссылки, чтобы узнать больше. 
<br/><br/>

|Средство/метод  |Описание  |
|---------|---------|
|**[Сведения об угрозах и управление уязвимостями панели](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** мониторинга в Центр безопасности в Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) |Панель мониторинга & управление уязвимостями предоставляет информацию, которую можно использовать для снижения воздействия и улучшения осанки безопасности вашей организации. <br/><br/>См. [& управление уязвимостями](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) [и обзор Центр безопасности в Microsoft Defender.](/microsoft-365/security/defender-endpoint/use)  |
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (рекомендуется)    |Microsoft Intune (Intune), компонент [Microsoft Endpoint Manager,](/mem/endpoint-manager-overview)фокусируется на управлении мобильными устройствами (MDM) и управлении мобильными приложениями (MAM). С помощью Intune вы контролируете использование устройств организации, включая мобильные телефоны, планшеты и ноутбуки. Вы также можете настроить определенные политики для управления приложениями. <br/><br/>См. [в этой записи Управление защитником Майкрософт для конечной точки с помощью Intune.](manage-atp-post-migration-intune.md)         |
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**     |Microsoft Endpoint Manager (Configuration Manager), ранее известный как System Center Configuration Manager, является компонентом [Microsoft Endpoint Manager](/mem/endpoint-manager-overview). Configuration Manager — это мощный инструмент управления пользователями, устройствами и программным обеспечением.<br/><br/>См. [в этой ссылке Управление защитником Майкрософт для конечной точки с помощью диспетчера конфигурации.](manage-atp-post-migration-configuration-manager.md)        |
|**[Объекты групповой политики в Azure Active Directory доменных службах](/azure/active-directory-domain-services/manage-group-policy)** |[Azure Active Directory domain Services](/azure/active-directory-domain-services/overview) включает встроенные объекты групповой политики для пользователей и устройств. Вы можете настроить встроенные объекты групповой политики по мере необходимости для среды, а также создать настраиваемые объекты групповой политики и организационные подразделения (OUs). <br/><br/>См. в этой ссылке Управление [защитником Майкрософт для конечной точки с объектами групповой политики.](manage-atp-post-migration-group-policy-objects.md) |
|**[PowerShell, WMI и MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*Рекомендуется использовать Microsoft Endpoint Manager (включая Intune и Configuration Manager) для управления функциями защиты от угроз на устройствах организации. Однако можно настроить некоторые параметры, например антивирусная программа в Microsoft Defender на отдельных устройствах (конечных точках) с помощью PowerShell, WMI или MPCmdRun.exe.*<br/><br/>Вы можете использовать PowerShell для управления антивирусная программа в Microsoft Defender, защиты от эксплуатации и правил уменьшения поверхности атаки. См. [в обзоре Настройка Защитника Майкрософт для конечной точки с помощью PowerShell.](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell)<br/><br/>Вы можете использовать Windows инструментов управления (WMI) для управления антивирусная программа в Microsoft Defender и исключений. См. [в настройках Microsoft Defender для конечной точки с WMI.](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)<br/><br/>Вы можете использовать службу microsoft Malware Protection Command-Line (MPCmdRun.exe) для управления антивирусная программа в Microsoft Defender и исключений, а также проверки подключений между сетью и облаком. См. [в настройках Microsoft Defender для конечной точки с помощью MPCmdRun.exe. ](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) |

## <a name="see-also"></a>См. также

- [Устранение ложных положительных/отрицательных срабатываний в Microsoft Defender для конечной точки](defender-endpoint-false-positives-negatives.md)
