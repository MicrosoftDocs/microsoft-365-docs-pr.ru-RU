---
title: Мониторинг и отчет об антивирусной защите Защитника Майкрософт
description: Используйте средства Configuration Manager или security information and event management (SIEM) для использования отчетов и мониторинга microsoft Defender AV с помощью PowerShell и WMI.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a31dfa7e5eba36937f4ab50205df938614e80b76
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765771"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Отчет об антивирусной программе в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Антивирус Microsoft Defender встроен в Windows 10, Windows Server 2019 и Windows Server 2016. Антивирус Microsoft Defender — это защита следующего поколения в Microsoft Defender для конечной точки. Защита следующего поколения помогает защитить устройства от угроз программного обеспечения, таких как вирусы, вредоносные программы и программы-шпионы в электронной почте, приложениях, облаке и Интернете.

С помощью антивируса Microsoft Defender у вас есть несколько вариантов проверки состояния защиты и оповещений. Вы можете использовать Microsoft Endpoint Manager для мониторинга [антивируса Microsoft Defender](/configmgr/protect/deploy-use/monitor-endpoint-protection) или [создания оповещений электронной почты.](/configmgr/protect/deploy-use/endpoint-configure-alerts) Или можно отслеживать защиту с помощью [Microsoft Intune.](/intune/introduction-intune)  

Пакет microsoft Operations Management Suite имеет надстройка [для](/windows/deployment/update/update-compliance-get-started) обновления соответствия требованиям, которая сообщает о ключевых проблемах антивируса Microsoft Defender, включая обновления защиты и параметры защиты в режиме реального времени.

Если у вас есть сервер сторонних сведений о безопасности и управлении событиями (SIEM), вы также можете потреблять Защитник Windows [событий клиента.](/windows/win32/events/windows-events) 

События Windows включают несколько источников событий безопасности, в том числе события Диспетчер учетной записи безопасности (sam) (расширенные для[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), также см. тему аудита безопасности) и события [](/windows/device-security/auditing/security-auditing-overview) [Защитник Windows.](troubleshoot-microsoft-defender-antivirus.md) 

Эти события можно централизованно агрегировать с помощью [сборщика событий Windows.](/windows/win32/wec/windows-event-collector) Часто серверы SIEM имеют соединители для событий Windows, что позволяет соотнести все события безопасности на сервере SIEM. 

Вы также можете отслеживать события вредоносных программ с помощью решения по оценке вредоносных [программ в журнале Analytics](/azure/log-analytics/log-analytics-malware).

Для мониторинга или определения состояния в PowerShell, WMI или Microsoft Azure см. в таблице [(Развертывание, управление и отчеты).](deploy-manage-report-microsoft-defender-antivirus.md#ref2)

## <a name="related-articles"></a>Статьи по теме

- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Антивирус Microsoft Defender на Windows Server 2016 и 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Развертывание антивируса Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)