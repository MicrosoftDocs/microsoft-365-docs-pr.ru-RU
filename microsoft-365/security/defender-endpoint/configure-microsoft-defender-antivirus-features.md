---
title: Настройка функций антивирусной программы в Microsoft Defender
description: Вы можете настроить антивирусная программа в Microsoft Defender с помощью Intune, Microsoft Endpoint Configuration Manager, групповой политики и PowerShell.
keywords: антивирусная программа в Microsoft Defender, антивирусное программное обеспечение, безопасность, защитник, настройка, конфигурация, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, управление мобильными устройствами, GP, групповой политики, PowerShell
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
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 7fa5959ede9f0c71c75cefafc0fcb0d4376a1a4f
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925399"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="5ec7b-104">Настройка функций антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5ec7b-104">Configure Microsoft Defender Antivirus features</span></span>


<span data-ttu-id="5ec7b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5ec7b-105">**Applies to:**</span></span>

- [<span data-ttu-id="5ec7b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5ec7b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5ec7b-107">Вы можете настроить антивирусная программа в Microsoft Defender с помощью нескольких инструментов, таких как:</span><span class="sxs-lookup"><span data-stu-id="5ec7b-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="5ec7b-108">Microsoft Endpoint Manager (которая включает Microsoft Intune и Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="5ec7b-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="5ec7b-109">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="5ec7b-109">Group Policy</span></span>
- <span data-ttu-id="5ec7b-110">Командлеты PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ec7b-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="5ec7b-111">Инструментарий управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="5ec7b-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="5ec7b-112">Можно настроить следующие широкие категории функций:</span><span class="sxs-lookup"><span data-stu-id="5ec7b-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="5ec7b-113">Защита с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-113">Cloud-delivered protection.</span></span> <span data-ttu-id="5ec7b-114">См. [облачные средства защиты и антивирусная программа в Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5ec7b-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="5ec7b-115">Защита в режиме реального времени в режиме реального времени, включая защиту на основе поведенческих, увристических и машинных учебных ок.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="5ec7b-116">См. [в перенастройке поведенческой, севристической и защиты в режиме реального времени.](configure-protection-features-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5ec7b-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="5ec7b-117">Взаимодействие конечных пользователей с клиентом на отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="5ec7b-118">См. следующие ресурсы:</span><span class="sxs-lookup"><span data-stu-id="5ec7b-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="5ec7b-119">Запретить пользователям видеть или взаимодействовать с антивирусная программа в Microsoft Defender пользовательским интерфейсом</span><span class="sxs-lookup"><span data-stu-id="5ec7b-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="5ec7b-120">Предотвращение или разрешение пользователям локального антивирусная программа в Microsoft Defender параметров политики</span><span class="sxs-lookup"><span data-stu-id="5ec7b-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="5ec7b-121">Просмотрите [справочные темы для средств управления и конфигурации.](configuration-management-reference-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5ec7b-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>
