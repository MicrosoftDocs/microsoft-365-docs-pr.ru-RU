---
title: Настройка функций антивируса Microsoft Defender
description: Можно настроить антивирусные функции Microsoft Defender с помощью Intune, Microsoft Endpoint Configuration Manager, Group Policy и PowerShell.
keywords: Антивирус Microsoft Defender, антивирус, защита, защита, настройка, конфигурация, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, управление мобильными устройствами, GP, групповой политики, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3dcf0ab24541a8837fbab91049fed0157b7f1fc9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690819"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="0aa82-104">Настройка функций антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0aa82-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0aa82-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0aa82-105">**Applies to:**</span></span>

- [<span data-ttu-id="0aa82-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0aa82-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0aa82-107">Антивирус Microsoft Defender можно настроить с помощью ряда средств, в том числе:</span><span class="sxs-lookup"><span data-stu-id="0aa82-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="0aa82-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0aa82-108">Microsoft Intune</span></span>
- <span data-ttu-id="0aa82-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0aa82-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="0aa82-110">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="0aa82-110">Group Policy</span></span>
- <span data-ttu-id="0aa82-111">Командлеты PowerShell</span><span class="sxs-lookup"><span data-stu-id="0aa82-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="0aa82-112">Инструментарий управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="0aa82-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="0aa82-113">Можно настроить следующие широкие категории функций:</span><span class="sxs-lookup"><span data-stu-id="0aa82-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="0aa82-114">Защита с облачным доставкой</span><span class="sxs-lookup"><span data-stu-id="0aa82-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="0aa82-115">Защита в режиме реального времени, включая защиту на основе поведенческих, увристических и машинных знаний</span><span class="sxs-lookup"><span data-stu-id="0aa82-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="0aa82-116">Взаимодействие конечных пользователей с клиентом на отдельных конечных точках</span><span class="sxs-lookup"><span data-stu-id="0aa82-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="0aa82-117">В следующих статьях описано, как выполнять ключевые задачи при настройке антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0aa82-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="0aa82-118">Каждая статья содержит инструкции для применимого средства конфигурации (или инструментов).</span><span class="sxs-lookup"><span data-stu-id="0aa82-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="0aa82-119">Статья</span><span class="sxs-lookup"><span data-stu-id="0aa82-119">Article</span></span>  |<span data-ttu-id="0aa82-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0aa82-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="0aa82-121">Использование антивирусной защиты Microsoft Defender с облачным обеспечением</span><span class="sxs-lookup"><span data-stu-id="0aa82-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="0aa82-122">Использование облачной защиты для быстрого и надежного обнаружения антивирусов.</span><span class="sxs-lookup"><span data-stu-id="0aa82-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="0aa82-123">Настройка поведенческой, севристической и защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="0aa82-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="0aa82-124">Включить антивирусную защиту на основе поведения, а также защиту от вирусов в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="0aa82-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="0aa82-125">Настройка взаимодействия между конечными пользователями с антивирусом Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0aa82-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="0aa82-126">Настройте, как конечные пользователи в организации взаимодействуют с антивирусом Microsoft Defender, какие уведомления они видят и могут ли они переопределять параметры.</span><span class="sxs-lookup"><span data-stu-id="0aa82-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="0aa82-127">Вы также можете просмотреть раздел [Справочные темы](configuration-management-reference-microsoft-defender-antivirus.md) для управления и инструментов конфигурации для обзора каждого средства и ссылок на дополнительную помощь.</span><span class="sxs-lookup"><span data-stu-id="0aa82-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>