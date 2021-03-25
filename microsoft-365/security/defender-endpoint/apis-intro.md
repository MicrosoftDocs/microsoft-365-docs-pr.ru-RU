---
title: Доступ к API конечных точек Microsoft Defender
ms.reviewer: ''
description: Узнайте, как можно использовать API для автоматизации рабочего процесса и инновация на основе возможностей ATP Защитника Майкрософт
keywords: apis, api, wdatp, open api, microsoft defender atp api, public api, supported apis, alerts, device, user, domain, ip, file, advanced hunting, query
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 70a8ba9d3ff864ca58c856714b00f0e8feba933a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164772"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="ff368-104">Доступ к API конечных точек Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ff368-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ff368-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ff368-105">**Applies to:**</span></span>
- [<span data-ttu-id="ff368-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ff368-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ff368-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff368-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="ff368-108">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ff368-108">**Applies to:**</span></span> 
- [<span data-ttu-id="ff368-109">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ff368-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="ff368-110">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ff368-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ff368-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ff368-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="ff368-112">Defender for Endpoint предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="ff368-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="ff368-113">Эти API позволят автоматизировать рабочий процесс и инновациям на основе возможностей Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="ff368-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="ff368-114">Доступ к API требует проверки подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="ff368-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="ff368-115">Дополнительные сведения см. в [тексте OAuth 2.0 Authorization Code Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="ff368-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="ff368-116">Просмотрите это видео для краткого обзора API Defender для API endpoint.</span><span class="sxs-lookup"><span data-stu-id="ff368-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="ff368-117">В общем, для использования API необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ff368-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="ff368-118">Создание приложения AAD</span><span class="sxs-lookup"><span data-stu-id="ff368-118">Create an AAD application</span></span>
- <span data-ttu-id="ff368-119">Получение маркера доступа с помощью этого приложения</span><span class="sxs-lookup"><span data-stu-id="ff368-119">Get an access token using this application</span></span>
- <span data-ttu-id="ff368-120">Использование маркера для доступа к API Defender для endpoint</span><span class="sxs-lookup"><span data-stu-id="ff368-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="ff368-121">Вы можете получить доступ к API Defender для конечной точки с **помощью контекста приложений** или **пользовательского контекста.**</span><span class="sxs-lookup"><span data-stu-id="ff368-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="ff368-122">**Контекст приложения: (Рекомендуется)**</span><span class="sxs-lookup"><span data-stu-id="ff368-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="ff368-123">Используется приложениями, которые работают без участия пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff368-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="ff368-124">например, приложения, которые работают в качестве фоновых служб или daemons.</span><span class="sxs-lookup"><span data-stu-id="ff368-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="ff368-125">Действия, которые необходимо предпринять для доступа к API Defender для конечной точки с контекстом приложения:</span><span class="sxs-lookup"><span data-stu-id="ff368-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="ff368-126">Создание веб-приложения AAD.</span><span class="sxs-lookup"><span data-stu-id="ff368-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="ff368-127">Назначьте нужное разрешение приложению, например, "Read Alerts", "Isolate Machines".</span><span class="sxs-lookup"><span data-stu-id="ff368-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="ff368-128">Создайте ключ для этого приложения.</span><span class="sxs-lookup"><span data-stu-id="ff368-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="ff368-129">Получение маркера с помощью приложения с его ключом.</span><span class="sxs-lookup"><span data-stu-id="ff368-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="ff368-130">Использование маркера для доступа к API ATP Защитника Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ff368-130">Use the token to access Microsoft Defender ATP API</span></span>

     <span data-ttu-id="ff368-131">Дополнительные сведения см. в [приложении Get access with application context.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="ff368-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="ff368-132">**Контекст пользователя:**</span><span class="sxs-lookup"><span data-stu-id="ff368-132">**User Context:**</span></span> <br>
    <span data-ttu-id="ff368-133">Используется для выполнения действий в API от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff368-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="ff368-134">Действия, которые необходимо предпринять для доступа к API Defender для конечной точки с контекстом приложения:</span><span class="sxs-lookup"><span data-stu-id="ff368-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="ff368-135">Создание приложения AAD.</span><span class="sxs-lookup"><span data-stu-id="ff368-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="ff368-136">Назначьте нужное разрешение приложению, например"Read Alerts", "Isolate Machines" и т.д.</span><span class="sxs-lookup"><span data-stu-id="ff368-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="ff368-137">Получение маркера с помощью приложения с учетными данными пользователей.</span><span class="sxs-lookup"><span data-stu-id="ff368-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="ff368-138">Использование маркера для доступа к API ATP Защитника Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ff368-138">Use the token to access Microsoft Defender ATP API</span></span>

     <span data-ttu-id="ff368-139">Дополнительные сведения см. в [ссылке Получить доступ к пользовательскому контексту.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="ff368-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="ff368-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ff368-140">Related topics</span></span>
- [<span data-ttu-id="ff368-141">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="ff368-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="ff368-142">Доступ к Microsoft Defender для конечной точки с контекстом приложений</span><span class="sxs-lookup"><span data-stu-id="ff368-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="ff368-143">Доступ к Microsoft Defender для конечной точки с пользовательским контекстом</span><span class="sxs-lookup"><span data-stu-id="ff368-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
