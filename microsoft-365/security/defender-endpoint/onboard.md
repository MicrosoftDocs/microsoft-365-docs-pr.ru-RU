---
title: Настройка и управление возможностями Microsoft Defender для конечных точек
ms.reviewer: ''
description: Настройка и управление возможностями Microsoft Defender для конечных точек, таких как уменьшение поверхности атаки и защита следующего поколения
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3ad23e030048506784edd8f1988fa33263a085ae
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861339"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="1b61b-104">Настройка и управление возможностями Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="1b61b-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1b61b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1b61b-105">**Applies to:**</span></span>

- [<span data-ttu-id="1b61b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1b61b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1b61b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b61b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1b61b-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1b61b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1b61b-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1b61b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1b61b-110">Узнайте, как настроить и управлять функциями Defender для конечных точек, чтобы получить лучшую защиту безопасности для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1b61b-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="1b61b-111">Практические рекомендации по подключению новых устройств в организации см. в таблице [Onboard devices to the Microsoft Defender for Endpoint service.](./onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="1b61b-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1b61b-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1b61b-112">In this section</span></span>

<span data-ttu-id="1b61b-113">Статья</span><span class="sxs-lookup"><span data-stu-id="1b61b-113">Topic</span></span> | <span data-ttu-id="1b61b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1b61b-114">Description</span></span>
:---|:---
[<span data-ttu-id="1b61b-115">Настройка параметров Центра безопасности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b61b-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="1b61b-116">Настройка параметров, связанных с порталом, таких как общие параметры, расширенные функции или возможность предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="1b61b-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="1b61b-117">Настройка возможностей уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="1b61b-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="1b61b-118">Настройте возможности уменьшения поверхности атаки, чтобы убедиться, что параметры правильно применены, и заданная техника смягчения последствий.</span><span class="sxs-lookup"><span data-stu-id="1b61b-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="1b61b-119">Настройка защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="1b61b-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="1b61b-120">Настройте защиту следующего поколения, чтобы ловить все типы возникающих угроз.</span><span class="sxs-lookup"><span data-stu-id="1b61b-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="1b61b-121">Настройка возможностей экспертов по угрозам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1b61b-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="1b61b-122">Настройка и управление сведениями об угрозах кибербезопасности от экспертов Microsoft Threat.</span><span class="sxs-lookup"><span data-stu-id="1b61b-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="1b61b-123">Настройка интеграции Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1b61b-123">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="1b61b-124">Настройка других решений, интегрируемых с Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1b61b-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="1b61b-125">Поддержка управления и API</span><span class="sxs-lookup"><span data-stu-id="1b61b-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="1b61b-126">Извлеките оповещения в службу управления сведениями о безопасности и событиями (SIEM) или используйте API для создания настраиваемой оповещений.</span><span class="sxs-lookup"><span data-stu-id="1b61b-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="1b61b-127">Создание и создание отчетов Power BI.</span><span class="sxs-lookup"><span data-stu-id="1b61b-127">Create and build Power BI reports.</span></span>
