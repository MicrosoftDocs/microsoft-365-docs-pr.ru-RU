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
- m365-initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 774f3af001800f01ce956097f6b7441df2c0ddac
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413476"
---
# <a name="configure-and-manage-microsoft-defender-atp-capabilities"></a><span data-ttu-id="0192c-104">Настройка возможностей пакета ATP для защитника Майкрософт и управление ими</span><span class="sxs-lookup"><span data-stu-id="0192c-104">Configure and manage Microsoft Defender ATP capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0192c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0192c-105">**Applies to:**</span></span>

- [<span data-ttu-id="0192c-106">Microsoft Defender Advanced Threat Protection (ATP в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="0192c-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="0192c-107">Настройте все возможности пакета ATP для защитника Майкрософт и управляйте ими, чтобы получить лучшую защиту в Организации.</span><span class="sxs-lookup"><span data-stu-id="0192c-107">Configure and manage all the Microsoft Defender ATP capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="0192c-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0192c-108">In this section</span></span> 
<span data-ttu-id="0192c-109">Статья</span><span class="sxs-lookup"><span data-stu-id="0192c-109">Topic</span></span> | <span data-ttu-id="0192c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0192c-110">Description</span></span> 
:---|:---
[<span data-ttu-id="0192c-111">Настройка возможностей по уменьшению уязвимой зоны</span><span class="sxs-lookup"><span data-stu-id="0192c-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="0192c-112">Обеспечивая правильную настройку параметров конфигурации и применение методик, связанных с устранением проблем, эти возможности выдают резисторы и используют их.</span><span class="sxs-lookup"><span data-stu-id="0192c-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitations.</span></span> 
[<span data-ttu-id="0192c-113">Настройка защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="0192c-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="0192c-114">Настройте защиту следующего поколения для перехвата всех типов новых угроз.</span><span class="sxs-lookup"><span data-stu-id="0192c-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="0192c-115">Настройка возможностей экспертов по угрозам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0192c-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="0192c-116">Настраивать и управлять тем, как вы хотели бы получать циберсекуритиную логику угроз от экспертов Майкрософт по угрозе.</span><span class="sxs-lookup"><span data-stu-id="0192c-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="0192c-117">Настройка интеграции Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="0192c-117">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="0192c-118">Настройка других решений, которые интегрируются с защитником Майкрософт ATP.</span><span class="sxs-lookup"><span data-stu-id="0192c-118">Configure other solutions that integrate with Microsoft Defender ATP.</span></span>
[<span data-ttu-id="0192c-119">Поддержка управления и API</span><span class="sxs-lookup"><span data-stu-id="0192c-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="0192c-120">Получение оповещений о SIEM или использование API для создания настраиваемых оповещений.</span><span class="sxs-lookup"><span data-stu-id="0192c-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="0192c-121">Создавайте и создавайте отчеты Power BI.</span><span class="sxs-lookup"><span data-stu-id="0192c-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="0192c-122">Настройка параметров центра безопасности защитника Microsoft</span><span class="sxs-lookup"><span data-stu-id="0192c-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="0192c-123">Настройка параметров, связанных с порталом, таких как общие параметры, расширенные функции, разрешение предварительной версии и других.</span><span class="sxs-lookup"><span data-stu-id="0192c-123">Configure portal related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



