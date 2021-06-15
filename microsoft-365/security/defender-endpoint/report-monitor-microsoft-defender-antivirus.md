---
title: Мониторинг и отчет о защите антивирусная программа в Microsoft Defender безопасности
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
ms.topic: article
ms.openlocfilehash: 91891af35def83f21b3db8c7e8fa4b320bef563c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926167"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Отчет об антивирусной программе в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

антивирусная программа в Microsoft Defender встроена в Windows 10, Windows Server 2019 и Windows Server 2016. антивирусная программа в Microsoft Defender защиты нового поколения в Microsoft Defender для конечной точки. Защита следующего поколения помогает защитить устройства от угроз программного обеспечения, таких как вирусы, вредоносные программы и программы-шпионы в электронной почте, приложениях, облаке и Интернете.

С антивирусная программа в Microsoft Defender у вас есть несколько вариантов проверки состояния защиты и оповещений. Вы можете использовать Microsoft Endpoint Manager [для мониторинга антивирусная программа в Microsoft Defender](/configmgr/protect/deploy-use/monitor-endpoint-protection) [или создания оповещений электронной почты.](/configmgr/protect/deploy-use/endpoint-configure-alerts) Или можно отслеживать защиту с [помощью Microsoft Intune.](/intune/introduction-intune)  

Пакет microsoft Operations Management Suite имеет надстройка [для](/windows/deployment/update/update-compliance-get-started) обновления соответствия требованиям, которая сообщает о ключевых антивирусная программа в Microsoft Defender, включая обновления защиты и параметры защиты в режиме реального времени.

Если у вас есть сторонний сервер управления данными о безопасности и событиями (SIEM), вы также можете использовать события Защитник Windows [клиента.](/windows/win32/events/windows-events) 

Windows событий включают несколько источников событий безопасности, в том числе события Диспетчер учетной записи [](/windows/device-security/auditing/security-auditing-overview) безопасности (SAM) (расширенные для[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), также см. тему аудита [безопасности) и события Защитник Windows](troubleshoot-microsoft-defender-antivirus.md). 

Эти события можно централизованно агрегировать с помощью [Windows событий.](/windows/win32/wec/windows-event-collector) Часто серверы SIEM имеют соединители для Windows событий, что позволяет соотносить все события безопасности на сервере SIEM. 

Вы также можете отслеживать события вредоносных программ с помощью решения по оценке вредоносных [программ в журнале Analytics](/azure/log-analytics/log-analytics-malware).

Для мониторинга или определения состояния в PowerShell, WMI или Microsoft Azure см. в таблице [(Развертывание,](deploy-manage-report-microsoft-defender-antivirus.md#ref2)управление и отчеты).

## <a name="related-articles"></a>Связанные статьи

- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Антивирусная программа в Microsoft Defender в Windows Server 2016 и 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Развертывание антивирусная программа в Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)