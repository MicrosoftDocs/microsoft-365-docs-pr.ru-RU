---
title: Настройка и управление защитником Майкрософт для возможностей конечных точек
ms.reviewer: ''
description: Настройка и управление защитником Майкрософт для обеспечения конечных точек, таких как снижение уязвимой зоны и защита следующего поколения
keywords: Настройка, управление, возможности, сокращение возможных направлений атак, защита следующего поколения, защита от обнаружения конечных точек и ответ, автоматическое исследование и исправление, элементы управления безопасностью, элементы управления
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: b202b30e218448794eac7588078ff3ac9cfe9ee3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844816"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="ba3f7-104">Настройка и управление защитником Майкрософт для возможностей конечных точек</span><span class="sxs-lookup"><span data-stu-id="ba3f7-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ba3f7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ba3f7-105">**Applies to:**</span></span>

- [<span data-ttu-id="ba3f7-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ba3f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="ba3f7-107">Настройте и управляйте всеми защитником Майкрософт для возможностей конечных точек, чтобы обеспечить лучшую защиту в Организации.</span><span class="sxs-lookup"><span data-stu-id="ba3f7-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="ba3f7-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ba3f7-108">In this section</span></span> 
<span data-ttu-id="ba3f7-109">Статья</span><span class="sxs-lookup"><span data-stu-id="ba3f7-109">Topic</span></span> | <span data-ttu-id="ba3f7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ba3f7-110">Description</span></span> 
:---|:---
[<span data-ttu-id="ba3f7-111">Настройка возможностей по уменьшению уязвимой зоны</span><span class="sxs-lookup"><span data-stu-id="ba3f7-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="ba3f7-112">Обеспечивая правильную настройку параметров конфигурации и применение методик преодоления последствий, эти возможности выделяются от атак на резисторы и в эксплуатацию.</span><span class="sxs-lookup"><span data-stu-id="ba3f7-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="ba3f7-113">Настройка защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="ba3f7-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="ba3f7-114">Настройте защиту следующего поколения для перехвата всех типов новых угроз.</span><span class="sxs-lookup"><span data-stu-id="ba3f7-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="ba3f7-115">Настройка возможностей экспертов по угрозам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ba3f7-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="ba3f7-116">Настраивать и управлять тем, как вы хотели бы получать циберсекуритиную логику угроз от экспертов Майкрософт по угрозе.</span><span class="sxs-lookup"><span data-stu-id="ba3f7-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="ba3f7-117">Настройка интеграции защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ba3f7-117">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="ba3f7-118">Настройка других решений, которые интегрируются с защитником Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ba3f7-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="ba3f7-119">Поддержка управления и API</span><span class="sxs-lookup"><span data-stu-id="ba3f7-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="ba3f7-120">Получение оповещений о SIEM или использование API для создания настраиваемых оповещений.</span><span class="sxs-lookup"><span data-stu-id="ba3f7-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="ba3f7-121">Создавайте и создавайте отчеты Power BI.</span><span class="sxs-lookup"><span data-stu-id="ba3f7-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="ba3f7-122">Настройка параметров центра безопасности защитника Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba3f7-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="ba3f7-123">Настройка параметров, относящихся к порталу, таких как общие параметры, расширенные функции, разрешение предварительной версии и других.</span><span class="sxs-lookup"><span data-stu-id="ba3f7-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



