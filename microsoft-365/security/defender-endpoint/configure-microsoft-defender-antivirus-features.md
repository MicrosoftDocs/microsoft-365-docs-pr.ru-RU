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
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275112"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="7e82f-104">Настройка функций антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7e82f-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7e82f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7e82f-105">**Applies to:**</span></span>

- [<span data-ttu-id="7e82f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7e82f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7e82f-107">Вы можете настроить антивирусная программа в Microsoft Defender с помощью нескольких инструментов, в том числе:</span><span class="sxs-lookup"><span data-stu-id="7e82f-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="7e82f-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7e82f-108">Microsoft Intune</span></span>
- <span data-ttu-id="7e82f-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7e82f-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="7e82f-110">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="7e82f-110">Group Policy</span></span>
- <span data-ttu-id="7e82f-111">Командлеты PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e82f-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="7e82f-112">Инструментарий управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="7e82f-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="7e82f-113">Можно настроить следующие широкие категории функций:</span><span class="sxs-lookup"><span data-stu-id="7e82f-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="7e82f-114">Облачная защита</span><span class="sxs-lookup"><span data-stu-id="7e82f-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="7e82f-115">Защита в режиме реального времени, включая защиту на основе поведенческих, увристических и машинных знаний</span><span class="sxs-lookup"><span data-stu-id="7e82f-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="7e82f-116">Взаимодействие конечных пользователей с клиентом на отдельных конечных точках</span><span class="sxs-lookup"><span data-stu-id="7e82f-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="7e82f-117">В следующих статьях описывается выполнение ключевых задач при настройке антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="7e82f-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="7e82f-118">Каждая статья содержит инструкции для применимого средства конфигурации (или инструментов).</span><span class="sxs-lookup"><span data-stu-id="7e82f-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="7e82f-119">Статья</span><span class="sxs-lookup"><span data-stu-id="7e82f-119">Article</span></span>  |<span data-ttu-id="7e82f-120">Описание</span><span class="sxs-lookup"><span data-stu-id="7e82f-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="7e82f-121">Использование облачной антивирусная программа в Microsoft Defender Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7e82f-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="7e82f-122">Использование облачной защиты для быстрого и надежного обнаружения антивирусов.</span><span class="sxs-lookup"><span data-stu-id="7e82f-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="7e82f-123">Настройка поведенческой, эвристической защиты и защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="7e82f-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="7e82f-124">Включить антивирусную защиту на основе поведения, а также защиту от вирусов в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="7e82f-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="7e82f-125">Настройка взаимодействия конечных пользователей с антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7e82f-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="7e82f-126">Настройте, как конечные пользователи в организации взаимодействуют с антивирусная программа в Microsoft Defender, какие уведомления они видят и могут ли они переопределять параметры.</span><span class="sxs-lookup"><span data-stu-id="7e82f-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="7e82f-127">Вы также можете просмотреть раздел [Справочные темы](configuration-management-reference-microsoft-defender-antivirus.md) для управления и инструментов конфигурации для обзора каждого средства и ссылок на дополнительную помощь.</span><span class="sxs-lookup"><span data-stu-id="7e82f-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>