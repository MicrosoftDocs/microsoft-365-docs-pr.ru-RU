---
title: Настройка возможностей конечных точек в Microsoft Defender и управление ими
ms.reviewer: ''
description: Настройка и управление Возможностями конечных точек в Microsoft Defender, такими как уменьшение поверхности атаки и защита нового поколения
keywords: настройка, управление, возможности, уменьшение поверхности атаки, защита нового поколения, средства управления безопасностью, обнаружение конечных точек и реагирование, автоматическое исследование и исправление, средства контроля безопасности, элементы управления
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: d04177ef38c1bd04b0b73e29de9d8ab6fc0893ce
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930130"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="f81d2-104">Настройка возможностей конечных точек в Microsoft Defender и управление ими</span><span class="sxs-lookup"><span data-stu-id="f81d2-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f81d2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f81d2-105">**Applies to:**</span></span>

- [<span data-ttu-id="f81d2-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f81d2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="f81d2-107">Настройте и управляйте всеми возможностями Конечной точки в Microsoft Defender для обеспечения наилучшей защиты системы безопасности для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f81d2-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="f81d2-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f81d2-108">In this section</span></span> 
<span data-ttu-id="f81d2-109">Статья</span><span class="sxs-lookup"><span data-stu-id="f81d2-109">Topic</span></span> | <span data-ttu-id="f81d2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f81d2-110">Description</span></span> 
:---|:---
[<span data-ttu-id="f81d2-111">Настройка возможностей сокращения поверхностей атаки</span><span class="sxs-lookup"><span data-stu-id="f81d2-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="f81d2-112">Убедившись, что параметры конфигурации настроены правильно и применяются методы противодействия эксплойту, эти наборы возможностей по-настоящему противяются атакам и атакам.</span><span class="sxs-lookup"><span data-stu-id="f81d2-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="f81d2-113">Настройка защиты нового поколения</span><span class="sxs-lookup"><span data-stu-id="f81d2-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="f81d2-114">Настройте защиту нового поколения, чтобы перехватить все типы возникающих угроз.</span><span class="sxs-lookup"><span data-stu-id="f81d2-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="f81d2-115">Настройка возможностей экспертов по угрозам (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f81d2-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="f81d2-116">Настройте и управляйте тем, как вы хотите получать аналитику киберугроз от экспертов по угрозам Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f81d2-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="f81d2-117">Настройка интеграции с Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f81d2-117">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="f81d2-118">Настройте другие решения, интегрируемые с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f81d2-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="f81d2-119">Поддержка управления и API</span><span class="sxs-lookup"><span data-stu-id="f81d2-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="f81d2-120">Извлеките оповещения в SIEM или используйте API для создания пользовательских оповещений.</span><span class="sxs-lookup"><span data-stu-id="f81d2-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="f81d2-121">Создание и создание отчетов Power BI.</span><span class="sxs-lookup"><span data-stu-id="f81d2-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="f81d2-122">Настройка параметров Центра безопасности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f81d2-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="f81d2-123">Настройте параметры, связанные с порталом, такие как общие параметры, расширенные функции, включить предварительный просмотр и другие.</span><span class="sxs-lookup"><span data-stu-id="f81d2-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



