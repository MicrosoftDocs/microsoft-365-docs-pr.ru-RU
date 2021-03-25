---
title: Настройка и управление возможностями Microsoft Defender для конечных точек
ms.reviewer: ''
description: Настройка и управление возможностями Microsoft Defender для конечной точки, такими как уменьшение поверхности атаки и защита следующего поколения
keywords: настройка, управление, возможности, уменьшение поверхности атаки, защита следующего поколения, средства управления безопасностью, обнаружение и реагирование конечных точек, автоматическое расследование и исправление, элементы управления безопасностью, элементы управления
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 95c462829b43ae41c1fe664b2313a716078baea7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072637"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="a8d3b-104">Настройка и управление возможностями Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="a8d3b-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a8d3b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a8d3b-105">**Applies to:**</span></span>

- [<span data-ttu-id="a8d3b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a8d3b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="a8d3b-107">Настройте и управляйте всеми возможностями Microsoft Defender для конечных точек, чтобы получить лучшую защиту безопасности для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a8d3b-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="a8d3b-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a8d3b-108">In this section</span></span> 
<span data-ttu-id="a8d3b-109">Статья</span><span class="sxs-lookup"><span data-stu-id="a8d3b-109">Topic</span></span> | <span data-ttu-id="a8d3b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a8d3b-110">Description</span></span> 
:---|:---
[<span data-ttu-id="a8d3b-111">Настройка возможностей уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="a8d3b-111">Configure attack surface reduction capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="a8d3b-112">Обеспечивая правильное настройку параметров конфигурации и применяя методы смягчения последствий, этот набор возможностей позволяет противостоять атакам и эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="a8d3b-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="a8d3b-113">Настройка защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="a8d3b-113">Configure next generation protection</span></span>](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="a8d3b-114">Настройте защиту следующего поколения, чтобы ловить все типы возникающих угроз.</span><span class="sxs-lookup"><span data-stu-id="a8d3b-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="a8d3b-115">Настройка возможностей экспертов по угрозам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a8d3b-115">Configure Microsoft Threat Experts capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="a8d3b-116">Настройка и управление сведениями об угрозах кибербезопасности от экспертов Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="a8d3b-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="a8d3b-117">Настройка интеграции Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8d3b-117">Configure Microsoft 365 Defender integration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="a8d3b-118">Настройка других решений, интегрируемых с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a8d3b-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="a8d3b-119">Поддержка управления и API</span><span class="sxs-lookup"><span data-stu-id="a8d3b-119">Management and API support</span></span>](/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="a8d3b-120">Потяните оповещения в SIEM или используйте API для создания настраиваемой оповещений.</span><span class="sxs-lookup"><span data-stu-id="a8d3b-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="a8d3b-121">Создание и создание отчетов Power BI.</span><span class="sxs-lookup"><span data-stu-id="a8d3b-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="a8d3b-122">Настройка параметров Центра безопасности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a8d3b-122">Configure Microsoft Defender Security Center settings</span></span>](/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="a8d3b-123">Настройка параметров, связанных с порталом, таких как общие параметры, расширенные функции, включить функции предварительного просмотра и другие.</span><span class="sxs-lookup"><span data-stu-id="a8d3b-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>