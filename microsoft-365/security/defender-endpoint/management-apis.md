---
title: Обзор управления и интерфейсов API
ms.reviewer: ''
description: Узнайте о средствах управления и категориях API в Microsoft Defender for Endpoint
keywords: onboarding, api, siem, rbac, access, portal, integration, investigation, response, entities, entity, user context, application context, streaming
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
ms.openlocfilehash: a57cebd2cb7d35f968ed9ddfa4d9215eac2182d6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934463"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="41dcd-104">Обзор управления и интерфейсов API</span><span class="sxs-lookup"><span data-stu-id="41dcd-104">Overview of management and APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41dcd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="41dcd-105">**Applies to:**</span></span>
- [<span data-ttu-id="41dcd-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="41dcd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="41dcd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41dcd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="41dcd-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="41dcd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="41dcd-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="41dcd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="41dcd-110">Defender for Endpoint поддерживает широкий спектр параметров, чтобы клиенты могли легко принять платформу.</span><span class="sxs-lookup"><span data-stu-id="41dcd-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span> 

<span data-ttu-id="41dcd-111">Признавая, что клиентские среды и структуры могут отличаться, Defender for Endpoint был создан с гибкостью и детализацией, чтобы соответствовать различным требованиям клиента.</span><span class="sxs-lookup"><span data-stu-id="41dcd-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span> 

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="41dcd-112">Вход в конечную точку и доступ к порталу</span><span class="sxs-lookup"><span data-stu-id="41dcd-112">Endpoint onboarding and portal access</span></span> 

<span data-ttu-id="41dcd-113">Встроенное устройство полностью интегрировано в Microsoft Endpoint Manager и Microsoft Intune для клиентских устройств и Azure Defender для серверных устройств, обеспечивая полный комплексный опыт настройки, развертывания и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="41dcd-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Defender for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="41dcd-114">Кроме того, Microsoft Defender для конечной точки поддерживает групповую политику и другие сторонние средства, используемые для управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="41dcd-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="41dcd-115">Defender for Endpoint обеспечивает тонкий контроль над тем, что пользователи с доступом к порталу могут видеть и делать с помощью гибкости управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="41dcd-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="41dcd-116">Модель RBAC поддерживает все вкусы структуры групп безопасности:</span><span class="sxs-lookup"><span data-stu-id="41dcd-116">The RBAC model supports all flavors of security teams structure:</span></span>
- <span data-ttu-id="41dcd-117">Глобально распределенные организации и группы безопасности</span><span class="sxs-lookup"><span data-stu-id="41dcd-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="41dcd-118">Многоуровневые группы операций по безопасности модели</span><span class="sxs-lookup"><span data-stu-id="41dcd-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="41dcd-119">Полностью сегрегация подразделений с одними централизованными группами глобальных операций безопасности</span><span class="sxs-lookup"><span data-stu-id="41dcd-119">Fully segregated divisions with single centralized global security operations teams</span></span> 

## <a name="available-apis"></a><span data-ttu-id="41dcd-120">Доступные API</span><span class="sxs-lookup"><span data-stu-id="41dcd-120">Available APIs</span></span>
<span data-ttu-id="41dcd-121">Решение Microsoft Defender для конечной точки построено на платформе, готовой к интеграции.</span><span class="sxs-lookup"><span data-stu-id="41dcd-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="41dcd-122">Defender for Endpoint предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="41dcd-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="41dcd-123">Эти API позволят автоматизировать рабочий процесс и инновациям на основе возможностей Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="41dcd-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![Изображение доступных API и интеграции в Microsoft Defender для конечной точки](images/mdatp-apis.png)  

<span data-ttu-id="41dcd-125">API Defender для конечных точек можно сгруппить на три:</span><span class="sxs-lookup"><span data-stu-id="41dcd-125">The Defender for Endpoint APIs can be grouped into three:</span></span>
- <span data-ttu-id="41dcd-126">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="41dcd-126">Microsoft Defender for Endpoint APIs</span></span> 
- <span data-ttu-id="41dcd-127">API потоковой передачи необработанных данных</span><span class="sxs-lookup"><span data-stu-id="41dcd-127">Raw data streaming API</span></span>
- <span data-ttu-id="41dcd-128">Интеграция SIEM</span><span class="sxs-lookup"><span data-stu-id="41dcd-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="41dcd-129">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="41dcd-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="41dcd-130">Defender for Endpoint предлагает многоуровневую модель API, которая предоставляет данные и возможности в структурированной, понятной и простой в использовании модели, выставленной через стандартную модель проверки подлинности и авторизации на основе Azure AD, позволяющую получать доступ в контексте пользователей или приложений SaaS.</span><span class="sxs-lookup"><span data-stu-id="41dcd-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="41dcd-131">Модель API предназначена для последовательного использования сущностями и возможностями.</span><span class="sxs-lookup"><span data-stu-id="41dcd-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span> 

<span data-ttu-id="41dcd-132">Просмотрите это видео для краткого обзора API Defender для API endpoint.</span><span class="sxs-lookup"><span data-stu-id="41dcd-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="41dcd-133">**API** исследования предоставляет богатство Defender для конечной точки — разоблачение вычисляемого или "профилного" сущностей (например, устройств, пользователей и файлов) и дискретных событий (например, создания процессов и создания файлов), которые обычно описывают поведение, связанное с объектом, позволяя доступ к данным с помощью интерфейсов расследования, позволяющих получать доступ к данным на основе запросов.</span><span class="sxs-lookup"><span data-stu-id="41dcd-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="41dcd-134">Дополнительные сведения см. в [поддерживаемых API.](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="41dcd-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="41dcd-135">API **ответа** предоставляет возможность выполнять действия в службе и на устройствах, позволяя клиентам гнать индикаторы, управлять настройками, состоянием оповещения, а также принимать меры реагирования на устройствах программным образом, таких как изолирование устройств от сети, файлы карантина и другие.</span><span class="sxs-lookup"><span data-stu-id="41dcd-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span> 

## <a name="raw-data-streaming-api"></a><span data-ttu-id="41dcd-136">API потоковой передачи необработанных данных</span><span class="sxs-lookup"><span data-stu-id="41dcd-136">Raw data streaming API</span></span> 
<span data-ttu-id="41dcd-137">API потоковой передачи необработанных данных Defender для конечных точек предоставляет клиентам возможность отгрузки событий и оповещений в режиме реального времени из своих экземпляров по мере их возникновения в едином потоке данных, обеспечивая низкую задержку и механизм доставки высокой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="41dcd-137">Defender for Endpoint raw data streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="41dcd-138">Сведения о событиях Defender for Endpoint перенадвигаются непосредственно в хранилище Azure для долгосрочного хранения данных или в центры событий Azure для использования службами визуализации или дополнительными двигателями обработки данных.</span><span class="sxs-lookup"><span data-stu-id="41dcd-138">The Defender for Endpoint event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span> 

<span data-ttu-id="41dcd-139">Дополнительные сведения см. в [API потоковой передачи необработанных данных.](raw-data-export.md)</span><span class="sxs-lookup"><span data-stu-id="41dcd-139">For more information, see [Raw data streaming API](raw-data-export.md).</span></span>


## <a name="siem-api"></a><span data-ttu-id="41dcd-140">SIEM API</span><span class="sxs-lookup"><span data-stu-id="41dcd-140">SIEM API</span></span>
<span data-ttu-id="41dcd-141">При включении интеграции сведений о безопасности и управлении событиями (SIEM) это позволяет извлекть обнаружения из Центра безопасности Microsoft Defender с помощью решения SIEM или напрямую подключаясь к API REST обнаружения.</span><span class="sxs-lookup"><span data-stu-id="41dcd-141">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="41dcd-142">Это активирует раздел сведений о доступе к соединителем SIEM с предварительно заселяемыми значениями, и приложение создается под клиентом Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="41dcd-142">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="41dcd-143">Дополнительные сведения см. в [см. в деле интеграции SIEM.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="41dcd-143">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="41dcd-144">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="41dcd-144">Related topics</span></span>
- [<span data-ttu-id="41dcd-145">Доступ к API конечных точек Microsoft Defender </span><span class="sxs-lookup"><span data-stu-id="41dcd-145">Access the Microsoft Defender for Endpoint APIs </span></span>](apis-intro.md)
- [<span data-ttu-id="41dcd-146">Поддерживаемые API</span><span class="sxs-lookup"><span data-stu-id="41dcd-146">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="41dcd-147">Возможности для технических партнеров</span><span class="sxs-lookup"><span data-stu-id="41dcd-147">Technical partner opportunities</span></span>](partner-integration.md)

