---
title: Включить и настроить функции защиты от антивируса Microsoft Defender
description: Включить защиту на основе поведения, а также в режиме реального времени в Microsoft Defender AV.
keywords: heuristic, machine-learning, behaviour monitor, real-time protection, always-on, Microsoft Defender Antivirus, antimalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7a0e0571445e8ec753c3813a81dbcca9c698e7df
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690879"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="4ea02-104">Настройка поведенческой, севристической и защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="4ea02-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4ea02-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4ea02-105">**Applies to:**</span></span>

- [<span data-ttu-id="4ea02-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4ea02-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4ea02-107">Антивирус Microsoft Defender использует несколько методов для защиты от угроз:</span><span class="sxs-lookup"><span data-stu-id="4ea02-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="4ea02-108">Облачная защита для мгновенного обнаружения и блокировки новых и возникающих угроз</span><span class="sxs-lookup"><span data-stu-id="4ea02-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="4ea02-109">Всегда на сканирование, с помощью мониторинга поведения файлов и процессов и других heuristics (также известный как "защита в режиме реального времени")</span><span class="sxs-lookup"><span data-stu-id="4ea02-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="4ea02-110">Специальные обновления защиты на основе машинного обучения, ручного и автоматизированного анализа больших данных, а также комплексного исследования защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="4ea02-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="4ea02-111">Можно настроить, как антивирус Microsoft Defender использует эти методы с помощью групповой политики, управления конфигурацией центра систем, cmdlets PowerShell и инструментов управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="4ea02-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="4ea02-112">В этом разделе описывается конфигурация для постоянного сканирования, включая обнаружение и блокировку приложений, которые считаются небезопасными, но не могут быть обнаружены в качестве вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="4ea02-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="4ea02-113">См. в рубке Использование антивирусных технологий [Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) следующего поколения с помощью облачной защиты для обеспечения и настройки облачной защиты антивирусной программы Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="4ea02-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4ea02-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4ea02-114">In this section</span></span>

 <span data-ttu-id="4ea02-115">Статья</span><span class="sxs-lookup"><span data-stu-id="4ea02-115">Topic</span></span> | <span data-ttu-id="4ea02-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4ea02-116">Description</span></span>
---|---
[<span data-ttu-id="4ea02-117">Обнаружение и блокировка потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="4ea02-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="4ea02-118">Обнаружение и блокировка нежелательных приложений в сети, таких как adware, модификаторы браузера и панели инструментов, а также вредоносные или поддельные антивирусные приложения</span><span class="sxs-lookup"><span data-stu-id="4ea02-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="4ea02-119">Включить и настроить возможности защиты от антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4ea02-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="4ea02-120">Включить и настроить функции мониторинга антивирусных вирусов Microsoft Defender в режиме реального времени, а также другие функции мониторинга вирусов, которые всегда на стороне Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="4ea02-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>