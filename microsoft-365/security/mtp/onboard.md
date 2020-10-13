---
title: Настройка возможностей пакета ATP для защитника Майкрософт и управление ими
ms.reviewer: ''
description: Настройка и Управление возможностями Microsoft Defender ATP, таких как сокращение возможных направлений атак, защита от следующего поколения и контроль безопасности
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
ms.openlocfilehash: 64c6e5f7eefad50aa59301de3fd46cae60d6876f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429435"
---
# <a name="configure-and-manage-microsoft-defender-atp-capabilities"></a><span data-ttu-id="26a7e-104">Настройка возможностей пакета ATP для защитника Майкрософт и управление ими</span><span class="sxs-lookup"><span data-stu-id="26a7e-104">Configure and manage Microsoft Defender ATP capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="26a7e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="26a7e-105">**Applies to:**</span></span>

- [<span data-ttu-id="26a7e-106">Microsoft Defender Advanced Threat Protection (ATP в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="26a7e-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="26a7e-107">Настройте все возможности пакета ATP для защитника Майкрософт и управляйте ими, чтобы получить лучшую защиту в Организации.</span><span class="sxs-lookup"><span data-stu-id="26a7e-107">Configure and manage all the Microsoft Defender ATP capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="26a7e-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="26a7e-108">In this section</span></span> 
<span data-ttu-id="26a7e-109">Статья</span><span class="sxs-lookup"><span data-stu-id="26a7e-109">Topic</span></span> | <span data-ttu-id="26a7e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="26a7e-110">Description</span></span> 
:---|:---
[<span data-ttu-id="26a7e-111">Настройка возможностей по уменьшению уязвимой зоны</span><span class="sxs-lookup"><span data-stu-id="26a7e-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="26a7e-112">Обеспечивая правильную настройку параметров конфигурации и применение методик, связанных с устранением проблем, эти возможности выдают резисторы и используют их.</span><span class="sxs-lookup"><span data-stu-id="26a7e-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitations.</span></span> 
[<span data-ttu-id="26a7e-113">Настройка защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="26a7e-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="26a7e-114">Настройте защиту следующего поколения для перехвата всех типов новых угроз.</span><span class="sxs-lookup"><span data-stu-id="26a7e-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="26a7e-115">Настройка возможностей экспертов по угрозам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="26a7e-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="26a7e-116">Настраивать и управлять тем, как вы хотели бы получать циберсекуритиную логику угроз от экспертов Майкрософт по угрозе.</span><span class="sxs-lookup"><span data-stu-id="26a7e-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="26a7e-117">Настройка интеграции Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="26a7e-117">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="26a7e-118">Настройка других решений, которые интегрируются с защитником Майкрософт ATP.</span><span class="sxs-lookup"><span data-stu-id="26a7e-118">Configure other solutions that integrate with Microsoft Defender ATP.</span></span>
[<span data-ttu-id="26a7e-119">Поддержка управления и API</span><span class="sxs-lookup"><span data-stu-id="26a7e-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="26a7e-120">Получение оповещений о SIEM или использование API для создания настраиваемых оповещений.</span><span class="sxs-lookup"><span data-stu-id="26a7e-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="26a7e-121">Создавайте и создавайте отчеты Power BI.</span><span class="sxs-lookup"><span data-stu-id="26a7e-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="26a7e-122">Настройка параметров центра безопасности защитника Microsoft</span><span class="sxs-lookup"><span data-stu-id="26a7e-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="26a7e-123">Настройка параметров, связанных с порталом, таких как общие параметры, расширенные функции, разрешение предварительной версии и других.</span><span class="sxs-lookup"><span data-stu-id="26a7e-123">Configure portal related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



