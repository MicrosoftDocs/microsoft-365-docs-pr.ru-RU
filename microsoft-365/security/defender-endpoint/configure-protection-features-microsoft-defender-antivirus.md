---
title: Включить и настроить антивирусная программа в Microsoft Defender защиты
description: Включить защиту на основе поведения, а также в режиме реального времени в Microsoft Defender AV.
keywords: heuristic, machine-learning, behaviour monitor, real-time protection, always-on, антивирусная программа в Microsoft Defender, antimalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925567"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="cf844-104">Настройка поведенческой, эвристической защиты и защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="cf844-104">Configure behavioral, heuristic, and real-time protection</span></span>


<span data-ttu-id="cf844-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cf844-105">**Applies to:**</span></span>

- [<span data-ttu-id="cf844-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cf844-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cf844-107">антивирусная программа в Microsoft Defender использует несколько методов для защиты от угроз:</span><span class="sxs-lookup"><span data-stu-id="cf844-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="cf844-108">Облачная защита для мгновенного обнаружения и блокировки новых и возникающих угроз</span><span class="sxs-lookup"><span data-stu-id="cf844-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="cf844-109">Всегда на сканирование, с помощью мониторинга поведения файлов и процессов и других heuristics (также известный как "защита в режиме реального времени")</span><span class="sxs-lookup"><span data-stu-id="cf844-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="cf844-110">Специальные обновления защиты на основе машинного обучения, ручного и автоматизированного анализа больших данных, а также комплексного исследования защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="cf844-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="cf844-111">Вы можете настроить, как антивирусная программа в Microsoft Defender эти методы с помощью групповой политики, System Center управление конфигурацией, команды PowerShell и Windows инструментов управления (WMI).</span><span class="sxs-lookup"><span data-stu-id="cf844-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="cf844-112">В этом разделе описывается конфигурация для постоянного сканирования, включая обнаружение и блокировку приложений, которые считаются небезопасными, но не могут быть обнаружены в качестве вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="cf844-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="cf844-113">См. [в антивирусная программа в Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) технологий следующего поколения с помощью облачной защиты для обеспечения и настройки антивирусная программа в Microsoft Defender облачной защиты.</span><span class="sxs-lookup"><span data-stu-id="cf844-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cf844-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="cf844-114">In this section</span></span>

 <span data-ttu-id="cf844-115">Статья</span><span class="sxs-lookup"><span data-stu-id="cf844-115">Topic</span></span> | <span data-ttu-id="cf844-116">Описание</span><span class="sxs-lookup"><span data-stu-id="cf844-116">Description</span></span>
---|---
[<span data-ttu-id="cf844-117">Обнаружение и блокировка потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="cf844-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="cf844-118">Обнаружение и блокировка нежелательных приложений в сети, таких как adware, модификаторы браузера и панели инструментов, а также вредоносные или поддельные антивирусные приложения</span><span class="sxs-lookup"><span data-stu-id="cf844-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="cf844-119">Включить и настроить антивирусная программа в Microsoft Defender защиты</span><span class="sxs-lookup"><span data-stu-id="cf844-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="cf844-120">Включить и настроить защиту в режиме реального времени, юристику и другие функции антивирусная программа в Microsoft Defender мониторинга</span><span class="sxs-lookup"><span data-stu-id="cf844-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>
