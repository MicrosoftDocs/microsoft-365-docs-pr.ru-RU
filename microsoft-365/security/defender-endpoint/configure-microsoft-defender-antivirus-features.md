---
title: Настройка функций антивирусной программы в Microsoft Defender
description: Вы можете настроить антивирусная программа в Microsoft Defender с помощью Intune, Microsoft Endpoint Configuration Manager, групповой политики и PowerShell.
keywords: антивирусная программа в Microsoft Defender, антивирусное программное обеспечение, безопасность, защитник, настройка, конфигурация, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, управление мобильными устройствами, GP, групповой политики, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6ef9a2c34a88d7c9f5506c681088db9dc84cb0cc
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789031"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="82271-104">Настройка функций антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="82271-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="82271-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="82271-105">**Applies to:**</span></span>

- [<span data-ttu-id="82271-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="82271-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="82271-107">Вы можете настроить антивирусная программа в Microsoft Defender с помощью нескольких инструментов, таких как:</span><span class="sxs-lookup"><span data-stu-id="82271-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="82271-108">Microsoft Endpoint Manager (которая включает Microsoft Intune и Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="82271-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="82271-109">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="82271-109">Group Policy</span></span>
- <span data-ttu-id="82271-110">Командлеты PowerShell</span><span class="sxs-lookup"><span data-stu-id="82271-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="82271-111">Инструментарий управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="82271-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="82271-112">Можно настроить следующие широкие категории функций:</span><span class="sxs-lookup"><span data-stu-id="82271-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="82271-113">Защита с облачной доставкой.</span><span class="sxs-lookup"><span data-stu-id="82271-113">Cloud-delivered protection.</span></span> <span data-ttu-id="82271-114">См. [облачные средства защиты и антивирусная программа в Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="82271-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="82271-115">Защита в режиме реального времени в режиме реального времени, включая защиту на основе поведенческих, увристических и машинных учебных ок.</span><span class="sxs-lookup"><span data-stu-id="82271-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="82271-116">См. [в перенастройке поведенческой, севристической и защиты в режиме реального времени.](configure-protection-features-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="82271-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="82271-117">Взаимодействие конечных пользователей с клиентом на отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="82271-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="82271-118">См. следующие ресурсы:</span><span class="sxs-lookup"><span data-stu-id="82271-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="82271-119">Запретить пользователям видеть или взаимодействовать с антивирусная программа в Microsoft Defender пользовательским интерфейсом</span><span class="sxs-lookup"><span data-stu-id="82271-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="82271-120">Предотвращение или разрешение пользователям локального антивирусная программа в Microsoft Defender параметров политики</span><span class="sxs-lookup"><span data-stu-id="82271-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="82271-121">Просмотрите [справочные темы для средств управления и конфигурации.](configuration-management-reference-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="82271-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>