---
title: Обозреватель API в Microsoft Defender для конечной точки
ms.reviewer: ''
description: Использование обозревателя API для создания и создания запросов API, тестирования и отправки запросов для любого доступного API
keywords: api, explorer, send, request, get, post,
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
ms.custom: api
ms.openlocfilehash: 6a5684d71d34b3efdfe915ae674b4fcb90342154
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769801"
---
# <a name="api-explorer"></a><span data-ttu-id="30a8f-104">Обозреватель API</span><span class="sxs-lookup"><span data-stu-id="30a8f-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="30a8f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="30a8f-105">**Applies to:**</span></span>
- [<span data-ttu-id="30a8f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="30a8f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="30a8f-107">Обозреватель API конечных точек Microsoft Defender — это средство, которое помогает вам исследовать различные API-API Defender для конечных точек в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="30a8f-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="30a8f-108">Обозреватель API позволяет легко создавать и делать запросы API, тестировать и отправлять запросы для любой доступной конечной точки API Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="30a8f-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="30a8f-109">Используйте обозреватель API, чтобы принять меры или найти данные, которые могут еще не быть доступны через пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="30a8f-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="30a8f-110">Этот инструмент полезен при разработке приложения.</span><span class="sxs-lookup"><span data-stu-id="30a8f-110">The tool is useful during app development.</span></span> <span data-ttu-id="30a8f-111">Это позволяет выполнять запросы API, которые уважают параметры доступа пользователей, сокращая потребность в создании маркеров доступа.</span><span class="sxs-lookup"><span data-stu-id="30a8f-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="30a8f-112">С помощью этого средства можно изучить галерею примерных запросов, скопировать примеры кода результатов и создать сведения о отлаговке.</span><span class="sxs-lookup"><span data-stu-id="30a8f-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="30a8f-113">С помощью обозревателя API можно:</span><span class="sxs-lookup"><span data-stu-id="30a8f-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="30a8f-114">Выполнить запросы для любого метода и увидеть ответы в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="30a8f-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="30a8f-115">Быстро просмотрите примеры API и узнайте, какие параметры они поддерживают</span><span class="sxs-lookup"><span data-stu-id="30a8f-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="30a8f-116">С легкостью делайте вызовы API; нет необходимости проверки подлинности за пределами входного знака портала управления</span><span class="sxs-lookup"><span data-stu-id="30a8f-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="30a8f-117">Обозреватель API доступа</span><span class="sxs-lookup"><span data-stu-id="30a8f-117">Access API Explorer</span></span>

<span data-ttu-id="30a8f-118">В левом меню навигации **выберите &**  >  **API Explorer API.**</span><span class="sxs-lookup"><span data-stu-id="30a8f-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="30a8f-119">Поддерживаемые API</span><span class="sxs-lookup"><span data-stu-id="30a8f-119">Supported APIs</span></span>

<span data-ttu-id="30a8f-120">Обозреватель API поддерживает все API, предлагаемые Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="30a8f-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="30a8f-121">Список поддерживаемых API доступен в документации [API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="30a8f-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="30a8f-122">Начало работы с обозревателем API</span><span class="sxs-lookup"><span data-stu-id="30a8f-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="30a8f-123">В левой области имеется список примеров запросов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="30a8f-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="30a8f-124">Следуйте ссылкам и нажмите **кнопку Выполнить запрос**.</span><span class="sxs-lookup"><span data-stu-id="30a8f-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="30a8f-125">В некоторых примерах может потребоваться указать параметр в URL-адресе, например {machine-ID}.</span><span class="sxs-lookup"><span data-stu-id="30a8f-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="30a8f-126">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="30a8f-126">FAQ</span></span>

<span data-ttu-id="30a8f-127">**Нужно ли иметь маркер API для использования обозревателя API?**</span><span class="sxs-lookup"><span data-stu-id="30a8f-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="30a8f-128">Учетные данные для доступа к API не нужны.</span><span class="sxs-lookup"><span data-stu-id="30a8f-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="30a8f-129">Обозреватель API использует маркер портала управления Defender для конечных точек всякий раз, когда он делает запрос.</span><span class="sxs-lookup"><span data-stu-id="30a8f-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="30a8f-130">Учетные данные проверки подлинности пользователей, зарегистрированные в журнале, используются для проверки того, что обозреватель API уполномочен получать доступ к данным от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="30a8f-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="30a8f-131">Конкретные запросы API ограничены в зависимости от ваших привилегий RBAC.</span><span class="sxs-lookup"><span data-stu-id="30a8f-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="30a8f-132">Например, запрос на "Отправить индикатор" ограничен ролью администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="30a8f-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 
