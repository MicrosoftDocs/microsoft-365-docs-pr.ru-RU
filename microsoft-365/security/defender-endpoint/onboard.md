---
title: Настройка и управление возможностями Microsoft Defender для конечных точек
ms.reviewer: ''
description: Настройка и управление возможностями Microsoft Defender для конечных точек, таких как уменьшение поверхности атаки и защита следующего поколения
keywords: настройка, управление, возможности, уменьшение поверхности атаки, защита следующего поколения, средства управления безопасностью, обнаружение и нейтрализация атак на конечные точки, автоматическое расследование и исправление, элементы управления безопасностью, элементы управления
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
ms.technology: mde
ms.openlocfilehash: c58d7d4192afd0aa13a5ffb0c7f3204b4eaf0315
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844410"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="e5272-104">Настройка и управление возможностями Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="e5272-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e5272-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e5272-105">**Applies to:**</span></span>

- [<span data-ttu-id="e5272-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e5272-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e5272-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5272-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e5272-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e5272-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e5272-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e5272-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e5272-110">Узнайте, как настроить и управлять функциями Defender для конечных точек, чтобы получить лучшую защиту безопасности для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e5272-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="e5272-111">Практические рекомендации по подключению новых устройств в организации см. в таблице [Onboard devices to the Microsoft Defender for Endpoint service.](./onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="e5272-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e5272-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e5272-112">In this section</span></span>

<span data-ttu-id="e5272-113">Статья</span><span class="sxs-lookup"><span data-stu-id="e5272-113">Topic</span></span> | <span data-ttu-id="e5272-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e5272-114">Description</span></span>
:---|:---
[<span data-ttu-id="e5272-115">Настройка Центр безопасности в Microsoft Defender параметров</span><span class="sxs-lookup"><span data-stu-id="e5272-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="e5272-116">Настройка параметров, связанных с порталом, таких как общие параметры, расширенные функции или возможность предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="e5272-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="e5272-117">Настройка возможностей сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="e5272-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="e5272-118">Настройте возможности уменьшения поверхности атаки, чтобы убедиться, что параметры правильно применены, и заданная техника смягчения последствий.</span><span class="sxs-lookup"><span data-stu-id="e5272-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="e5272-119">Настройка защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="e5272-119">Configure next-generation protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="e5272-120">Настройте защиту следующего поколения, чтобы ловить все типы возникающих угроз.</span><span class="sxs-lookup"><span data-stu-id="e5272-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="e5272-121">Настройка эксперты Майкрософт по угрозам возможностей</span><span class="sxs-lookup"><span data-stu-id="e5272-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="e5272-122">Настройка и управление данными об угрозах кибербезопасности с эксперты Майкрософт по угрозам.</span><span class="sxs-lookup"><span data-stu-id="e5272-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="e5272-123">Настройка интеграции Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5272-123">Configure Microsoft 365 Defender integration</span></span>](/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="e5272-124">Настройка других решений, интегрируемых с Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e5272-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="e5272-125">Поддержка управления и API</span><span class="sxs-lookup"><span data-stu-id="e5272-125">Management and API support</span></span>](/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="e5272-126">Извлеките оповещения в службу управления сведениями о безопасности и событиями (SIEM) или используйте API для создания настраиваемой оповещений.</span><span class="sxs-lookup"><span data-stu-id="e5272-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="e5272-127">Создание и создание Power BI отчетов.</span><span class="sxs-lookup"><span data-stu-id="e5272-127">Create and build Power BI reports.</span></span>
