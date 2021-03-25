---
title: Возможности и сценарии партнеров ATP Защитника Майкрософт
ms.reviewer: ''
description: Узнайте, как расширить существующие предложения по безопасности поверх открытой инфраструктуры и богатого набора API для создания расширений и интеграций с ATP Microsoft Defender
keywords: API, partner, extend, open framework, apis, extensions, integrations, detection, management, response, vulnerabilities, intelligence
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
ms.openlocfilehash: 1db82afa06fd0b6b3d7228aaf3020c5496ed69e7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186897"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a><span data-ttu-id="c3735-104">Возможности и сценарии партнеров Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="c3735-104">Microsoft Defender for Endpoint partner opportunities and scenarios</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c3735-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c3735-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3735-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c3735-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c3735-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3735-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="c3735-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c3735-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c3735-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c3735-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="c3735-110">Партнеры могут легко расширить существующие предложения по безопасности поверх открытой инфраструктуры и богатого и полного набора API для создания расширений и интеграций с Defender для endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3735-110">Partners can easily extend their existing security offerings on top of the open framework and a rich and complete set of APIs to build extensions and integrations with Defender for Endpoint.</span></span> 

<span data-ttu-id="c3735-111">API охватывают функциональные области, включая обнаружение, управление, ответ, уязвимости и широкий диапазон случаев использования для разведданных.</span><span class="sxs-lookup"><span data-stu-id="c3735-111">The APIs span functional areas including detection, management, response, vulnerabilities, and intelligence-wide range of use cases.</span></span> <span data-ttu-id="c3735-112">В зависимости от случая использования и необходимости партнеры могут передавать или запрашивать данные из Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c3735-112">Based on the use case and need, partners can either stream or query data from Defender for Endpoint.</span></span> 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a><span data-ttu-id="c3735-113">Сценарий 1. Корреляция внешних оповещений и автоматическое расследование и исправление</span><span class="sxs-lookup"><span data-stu-id="c3735-113">Scenario 1: External alert correlation and Automated investigation and remediation</span></span>
<span data-ttu-id="c3735-114">Defender for Endpoint предлагает уникальные возможности автоматического расследования и устранения последствий для масштабирования реагирования на инциденты.</span><span class="sxs-lookup"><span data-stu-id="c3735-114">Defender for Endpoint offers unique automated investigation and remediation capabilities to drive incident response at scale.</span></span> 

<span data-ttu-id="c3735-115">Интеграция возможностей автоматического расследования и реагирования с другими решениями, такими как продукты сетевой безопасности или другие продукты безопасности конечной точки, поможет в устранении оповещений.</span><span class="sxs-lookup"><span data-stu-id="c3735-115">Integrating the automated investigation and response capability with other solutions such as network security products or other endpoint security products will help to address alerts.</span></span> <span data-ttu-id="c3735-116">Интеграция также минимизирует сложности, связанные с корреляцией сигналов сети и устройств, эффективно упорядочение действий по расследованию и устранению угроз на устройствах.</span><span class="sxs-lookup"><span data-stu-id="c3735-116">The integration also minimizes the complexities surrounding network and device signal correlation, effectively streamlining the investigation and threat remediation actions on devices.</span></span>

<span data-ttu-id="c3735-117">Defender for Endpoint добавляет поддержку для этого сценария в следующих формах:</span><span class="sxs-lookup"><span data-stu-id="c3735-117">Defender for Endpoint adds support for this scenario in the following forms:</span></span>

- <span data-ttu-id="c3735-118">Внешние оповещений можно нажатие в Защитник для конечной точки и представлены бок о бок с дополнительными оповещениями на основе устройств от Защитника для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c3735-118">External alerts can be pushed into Defender for Endpoint and presented side by side with additional device-based alerts from Defender for Endpoint.</span></span> <span data-ttu-id="c3735-119">Это представление обеспечивает полный контекст оповещения — с реальным процессом и полным рассказом об атаке.</span><span class="sxs-lookup"><span data-stu-id="c3735-119">This view provides the full context of the alert - with the real process and the full story of attack.</span></span>

- <span data-ttu-id="c3735-120">После сгенерирования оповещений сигнал передается всем защищенным конечным точкам Defender для конечной точки предприятия.</span><span class="sxs-lookup"><span data-stu-id="c3735-120">Once an alert is generated, the signal is shared across all Defender for Endpoint protected endpoints in the enterprise.</span></span> <span data-ttu-id="c3735-121">Defender for Endpoint принимает незамедлимый автоматический или при помощи оператора ответ на предупреждение.</span><span class="sxs-lookup"><span data-stu-id="c3735-121">Defender for Endpoint takes immediate automated or operator-assisted response to address the alert.</span></span>

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a><span data-ttu-id="c3735-122">Сценарий 2. Интеграция системы управления безопасностью и автоматизации (SOAR)</span><span class="sxs-lookup"><span data-stu-id="c3735-122">Scenario 2: Security orchestration and automation response (SOAR) integration</span></span>
<span data-ttu-id="c3735-123">Решения для оркестровки могут помочь в создании книг и интеграции богатой модели данных и действий, которые API Defender для конечных точек подвергаются оркестровке ответов, таких как запрос для данных устройств, изоляция устройства, блок/разрешение, разрешение оповещения и другие.</span><span class="sxs-lookup"><span data-stu-id="c3735-123">Orchestration solutions can help build playbooks and integrate the rich data model and actions that Defender for Endpoint APIs expose to orchestrate responses, such as query for device data, trigger device isolation, block/allow, resolve alert and others.</span></span>

## <a name="scenario-3-indicators-matching"></a><span data-ttu-id="c3735-124">Сценарий 3. Соответствие индикаторам</span><span class="sxs-lookup"><span data-stu-id="c3735-124">Scenario 3: Indicators matching</span></span> 
<span data-ttu-id="c3735-125">Индикатор компрометации (IoCs) является важной функцией в каждом решении по защите конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c3735-125">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="c3735-126">Эта возможность доступна в Защитнике для конечной точки и дает возможность установить список показателей для предотвращения, обнаружения и исключения сущностями.</span><span class="sxs-lookup"><span data-stu-id="c3735-126">This capability is available in Defender for Endpoint and gives the ability to set a list of indicators for prevention, detection, and exclusion of entities.</span></span> <span data-ttu-id="c3735-127">Можно определить действия, которые необходимо принять, а также продолжительность применения действия.</span><span class="sxs-lookup"><span data-stu-id="c3735-127">One can define the action to be taken as well as the duration for when to apply the action.</span></span>

<span data-ttu-id="c3735-128">Вышеперечисленные сценарии служат примерами простого использования платформы.</span><span class="sxs-lookup"><span data-stu-id="c3735-128">The above scenarios serve as examples of the extensibility of the platform.</span></span> <span data-ttu-id="c3735-129">Примеры не ограничиваются, и мы рекомендуем использовать открытые рамки для обнаружения и изучения других сценариев.</span><span class="sxs-lookup"><span data-stu-id="c3735-129">You are not limited to the examples and we certainly encourage you to leverage the open framework to discover and explore other scenarios.</span></span>

<span data-ttu-id="c3735-130">Следуйте шагам [в стать партнером Microsoft Defender для конечной](get-started-partner-integration.md) точки, чтобы интегрировать решение в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3735-130">Follow the steps in [Become a Microsoft Defender for Endpoint partner](get-started-partner-integration.md) to integrate your solution in Defender for Endpoint.</span></span>

## <a name="related-topic"></a><span data-ttu-id="c3735-131">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="c3735-131">Related topic</span></span>
- [<span data-ttu-id="c3735-132">Обзор управления и API</span><span class="sxs-lookup"><span data-stu-id="c3735-132">Overview of management and APIs</span></span>](management-apis.md)
