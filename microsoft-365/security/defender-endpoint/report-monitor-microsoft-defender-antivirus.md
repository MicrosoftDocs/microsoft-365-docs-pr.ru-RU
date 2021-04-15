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
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="5ba19-104">Отчет об антивирусной программе в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5ba19-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5ba19-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5ba19-105">**Applies to:**</span></span>

- [<span data-ttu-id="5ba19-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5ba19-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5ba19-107">Антивирус Microsoft Defender встроен в Windows 10, Windows Server 2019 и Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="5ba19-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="5ba19-108">Антивирус Microsoft Defender — это защита следующего поколения в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5ba19-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="5ba19-109">Защита следующего поколения помогает защитить устройства от угроз программного обеспечения, таких как вирусы, вредоносные программы и программы-шпионы в электронной почте, приложениях, облаке и Интернете.</span><span class="sxs-lookup"><span data-stu-id="5ba19-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="5ba19-110">С помощью антивируса Microsoft Defender у вас есть несколько вариантов проверки состояния защиты и оповещений.</span><span class="sxs-lookup"><span data-stu-id="5ba19-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="5ba19-111">Вы можете использовать Microsoft Endpoint Manager для мониторинга [антивируса Microsoft Defender](/configmgr/protect/deploy-use/monitor-endpoint-protection) или [создания оповещений электронной почты.](/configmgr/protect/deploy-use/endpoint-configure-alerts)</span><span class="sxs-lookup"><span data-stu-id="5ba19-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="5ba19-112">Или можно отслеживать защиту с помощью [Microsoft Intune.](/intune/introduction-intune)</span><span class="sxs-lookup"><span data-stu-id="5ba19-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="5ba19-113">Пакет microsoft Operations Management Suite имеет надстройка [для](/windows/deployment/update/update-compliance-get-started) обновления соответствия требованиям, которая сообщает о ключевых проблемах антивируса Microsoft Defender, включая обновления защиты и параметры защиты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="5ba19-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="5ba19-114">Если у вас есть сервер сторонних сведений о безопасности и управлении событиями (SIEM), вы также можете потреблять Защитник Windows [событий клиента.](/windows/win32/events/windows-events)</span><span class="sxs-lookup"><span data-stu-id="5ba19-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="5ba19-115">События Windows включают несколько источников событий безопасности, в том числе события Диспетчер учетной записи безопасности (sam) (расширенные для[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), также см. тему аудита безопасности) и события [](/windows/device-security/auditing/security-auditing-overview) [Защитник Windows.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5ba19-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="5ba19-116">Эти события можно централизованно агрегировать с помощью [сборщика событий Windows.](/windows/win32/wec/windows-event-collector)</span><span class="sxs-lookup"><span data-stu-id="5ba19-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="5ba19-117">Часто серверы SIEM имеют соединители для событий Windows, что позволяет соотнести все события безопасности на сервере SIEM.</span><span class="sxs-lookup"><span data-stu-id="5ba19-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="5ba19-118">Вы также можете отслеживать события вредоносных программ с помощью решения по оценке вредоносных [программ в журнале Analytics](/azure/log-analytics/log-analytics-malware).</span><span class="sxs-lookup"><span data-stu-id="5ba19-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="5ba19-119">Для мониторинга или определения состояния в PowerShell, WMI или Microsoft Azure см. в таблице [(Развертывание, управление и отчеты).](deploy-manage-report-microsoft-defender-antivirus.md#ref2)</span><span class="sxs-lookup"><span data-stu-id="5ba19-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="5ba19-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5ba19-120">Related articles</span></span>

- [<span data-ttu-id="5ba19-121">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="5ba19-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="5ba19-122">Антивирус Microsoft Defender на Windows Server 2016 и 2019</span><span class="sxs-lookup"><span data-stu-id="5ba19-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="5ba19-123">Развертывание антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5ba19-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)