---
title: Настройка и управление возможностями ATP Защитника Microsoft Defender
ms.reviewer: ''
description: Настройка и управление возможностями ATP Защитника Microsoft Defender, такими как уменьшение поверхности атаки и защита следующего поколения
keywords: настройка, управление, возможности, уменьшение поверхности атаки, защита следующего поколения, средства управления безопасностью, обнаружение конечных точек и ответ, автоматическое расследование и исправление, элементы управления безопасностью, элементы управления
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a0872de9774773c136bca6febd621daba5b2d7d3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186381"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="db7bd-104">Настройка и управление возможностями Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="db7bd-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db7bd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="db7bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="db7bd-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="db7bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="db7bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db7bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="db7bd-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="db7bd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="db7bd-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="db7bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="db7bd-110">Настройка и управление всеми возможностями Defender для конечной точки, чтобы получить лучшую защиту безопасности для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="db7bd-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="db7bd-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="db7bd-111">In this section</span></span> 
<span data-ttu-id="db7bd-112">Статья</span><span class="sxs-lookup"><span data-stu-id="db7bd-112">Topic</span></span> | <span data-ttu-id="db7bd-113">Описание</span><span class="sxs-lookup"><span data-stu-id="db7bd-113">Description</span></span> 
:---|:---
[<span data-ttu-id="db7bd-114">Настройка возможностей уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="db7bd-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="db7bd-115">Обеспечивая правильное настройку параметров конфигурации и применяя методы смягчения последствий, этот набор возможностей позволяет противостоять атакам и эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="db7bd-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="db7bd-116">Настройка защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="db7bd-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="db7bd-117">Настройте защиту следующего поколения, чтобы ловить все типы возникающих угроз.</span><span class="sxs-lookup"><span data-stu-id="db7bd-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="db7bd-118">Настройка возможностей экспертов по угрозам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="db7bd-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="db7bd-119">Настройка и управление сведениями об угрозах кибербезопасности от экспертов Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="db7bd-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="db7bd-120">Настройка интеграции Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="db7bd-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="db7bd-121">Настройка других решений, интегрируемых с Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="db7bd-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="db7bd-122">Поддержка управления и API</span><span class="sxs-lookup"><span data-stu-id="db7bd-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="db7bd-123">Потяните оповещения в SIEM или используйте API для создания настраиваемой оповещений.</span><span class="sxs-lookup"><span data-stu-id="db7bd-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="db7bd-124">Создание и создание отчетов Power BI.</span><span class="sxs-lookup"><span data-stu-id="db7bd-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="db7bd-125">Настройка параметров Центра безопасности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="db7bd-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="db7bd-126">Настройка параметров, связанных с порталом, таких как общие параметры, расширенные функции, включить функции предварительного просмотра и другие.</span><span class="sxs-lookup"><span data-stu-id="db7bd-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>


