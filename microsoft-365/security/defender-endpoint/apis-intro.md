---
title: Доступ к API Microsoft Defender для конечной точки
ms.reviewer: ''
description: Узнайте, как можно использовать API для автоматизации рабочего процесса и инновация на основе возможностей Microsoft Defender для конечных точек
keywords: apis, api, wdatp, open api, microsoft defender for endpoint api, microsoft defender atp, public api, supported apis, alerts, device, user, domain, ip, file, advanced hunting, query
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 43c797dc8ee9f431ceda6ddecb0a1eada0e362f5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769657"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="24fb0-104">Доступ к API Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="24fb0-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="24fb0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="24fb0-105">**Applies to:**</span></span>
- [<span data-ttu-id="24fb0-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="24fb0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24fb0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24fb0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="24fb0-108">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="24fb0-108">**Applies to:**</span></span> 
- [<span data-ttu-id="24fb0-109">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="24fb0-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="24fb0-110">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="24fb0-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="24fb0-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="24fb0-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="24fb0-112">Defender for Endpoint предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="24fb0-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="24fb0-113">Эти API позволят автоматизировать рабочий процесс и инновациям на основе возможностей Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="24fb0-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="24fb0-114">Доступ к API требует проверки подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="24fb0-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="24fb0-115">Дополнительные сведения см. [в тексте OAuth 2.0 Authorization Code Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="24fb0-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="24fb0-116">Просмотрите это видео для краткого обзора API Defender для API endpoint.</span><span class="sxs-lookup"><span data-stu-id="24fb0-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="24fb0-117">В общем, для использования API необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="24fb0-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="24fb0-118">Создание [приложения AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="24fb0-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="24fb0-119">Получение маркера доступа с помощью этого приложения</span><span class="sxs-lookup"><span data-stu-id="24fb0-119">Get an access token using this application</span></span>
- <span data-ttu-id="24fb0-120">Использование маркера для доступа к API Defender для endpoint</span><span class="sxs-lookup"><span data-stu-id="24fb0-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="24fb0-121">Вы можете получить доступ к API Defender для конечной точки с **помощью контекста приложений** или **пользовательского контекста.**</span><span class="sxs-lookup"><span data-stu-id="24fb0-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="24fb0-122">**Контекст приложения: (Рекомендуется)**</span><span class="sxs-lookup"><span data-stu-id="24fb0-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="24fb0-123">Используется приложениями, которые работают без участия пользователя.</span><span class="sxs-lookup"><span data-stu-id="24fb0-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="24fb0-124">например, приложения, которые работают в качестве фоновых служб или daemons.</span><span class="sxs-lookup"><span data-stu-id="24fb0-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="24fb0-125">Действия, которые необходимо предпринять для доступа к API Defender для конечной точки с контекстом приложения:</span><span class="sxs-lookup"><span data-stu-id="24fb0-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="24fb0-126">Создание веб-приложения AAD.</span><span class="sxs-lookup"><span data-stu-id="24fb0-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="24fb0-127">Назначьте нужное разрешение приложению, например, "Read Alerts", "Isolate Machines".</span><span class="sxs-lookup"><span data-stu-id="24fb0-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="24fb0-128">Создайте ключ для этого приложения.</span><span class="sxs-lookup"><span data-stu-id="24fb0-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="24fb0-129">Получение маркера с помощью приложения с его ключом.</span><span class="sxs-lookup"><span data-stu-id="24fb0-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="24fb0-130">С помощью маркера можно получить доступ к API Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="24fb0-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="24fb0-131">Дополнительные сведения см. в [приложении Get access with application context.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="24fb0-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="24fb0-132">**Контекст пользователя:**</span><span class="sxs-lookup"><span data-stu-id="24fb0-132">**User Context:**</span></span> <br>
    <span data-ttu-id="24fb0-133">Используется для выполнения действий в API от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="24fb0-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="24fb0-134">Действия, которые необходимо предпринять для доступа к API Defender для конечной точки с контекстом приложения:</span><span class="sxs-lookup"><span data-stu-id="24fb0-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="24fb0-135">Создание приложения AAD.</span><span class="sxs-lookup"><span data-stu-id="24fb0-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="24fb0-136">Назначьте нужное разрешение приложению, например"Read Alerts", "Isolate Machines" и т.д.</span><span class="sxs-lookup"><span data-stu-id="24fb0-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="24fb0-137">Получение маркера с помощью приложения с учетными данными пользователей.</span><span class="sxs-lookup"><span data-stu-id="24fb0-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="24fb0-138">С помощью маркера можно получить доступ к API Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="24fb0-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="24fb0-139">Дополнительные сведения см. в [ссылке Получить доступ к пользовательскому контексту.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="24fb0-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="24fb0-140">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="24fb0-140">Related topics</span></span>
- [<span data-ttu-id="24fb0-141">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="24fb0-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="24fb0-142">Доступ к Microsoft Defender для конечной точки с контекстом приложений</span><span class="sxs-lookup"><span data-stu-id="24fb0-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="24fb0-143">Доступ к Microsoft Defender для конечной точки с пользовательским контекстом</span><span class="sxs-lookup"><span data-stu-id="24fb0-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
