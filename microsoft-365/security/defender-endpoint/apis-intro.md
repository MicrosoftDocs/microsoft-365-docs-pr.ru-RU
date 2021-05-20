---
title: Доступ к API Microsoft Defender для конечной точки
ms.reviewer: ''
description: Узнайте, как можно использовать API для автоматизации рабочих процессов и инноваций на основе возможностей Microsoft Defender for Endpoint
keywords: apis, api, wdatp, открытый api, Microsoft Defender для endpoint api, Microsoft Defender atp, public api, поддерживаемый apis, оповещения, устройство, пользователь, домен, ip, файл, продвинутая охота, запрос
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
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571833"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="a6796-104">Доступ к API Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a6796-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a6796-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a6796-105">**Applies to:**</span></span>
- [<span data-ttu-id="a6796-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a6796-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a6796-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6796-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="a6796-108">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a6796-108">**Applies to:**</span></span> 
- [<span data-ttu-id="a6796-109">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a6796-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="a6796-110">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a6796-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a6796-111">Подпишитесь на бесплатную пробную версию.</span><span class="sxs-lookup"><span data-stu-id="a6796-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="a6796-112">Defender for Endpoint предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="a6796-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="a6796-113">Эти API позволят автоматизировать рабочие процессы и внедрять инновации на основе возможностей Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a6796-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="a6796-114">Доступ к API требует проверки подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="a6796-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="a6796-115">Для получения дополнительной информации [см Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="a6796-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="a6796-116">Посмотрите это видео для краткого обзора API Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a6796-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="a6796-117">Как правило, необходимо предпринять следующие шаги для использования API:</span><span class="sxs-lookup"><span data-stu-id="a6796-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="a6796-118">Создание [приложения AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="a6796-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="a6796-119">Получить токен доступа с помощью этого приложения</span><span class="sxs-lookup"><span data-stu-id="a6796-119">Get an access token using this application</span></span>
- <span data-ttu-id="a6796-120">Используйте токен для доступа к Defender для API конечной точки</span><span class="sxs-lookup"><span data-stu-id="a6796-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="a6796-121">Вы можете получить доступ к API Defender for Endpoint с **контекстом приложения или** **контекстом пользователя.**</span><span class="sxs-lookup"><span data-stu-id="a6796-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="a6796-122">**Контекст приложения: (Рекомендуемый)**</span><span class="sxs-lookup"><span data-stu-id="a6796-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="a6796-123">Используется приложениями, которые работают без ва-во всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="a6796-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="a6796-124">например, приложения, которые работают в качестве фоновых служб или daemons.</span><span class="sxs-lookup"><span data-stu-id="a6796-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="a6796-125">Шаги, которые необходимо предпринять для доступа к API Defender for Endpoint с контекстом приложения:</span><span class="sxs-lookup"><span data-stu-id="a6796-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="a6796-126">Создание веб-приложения AAD.</span><span class="sxs-lookup"><span data-stu-id="a6796-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="a6796-127">Назначьте желаемое разрешение приложению, например, 'Read Alerts', 'Isolate Machines'.</span><span class="sxs-lookup"><span data-stu-id="a6796-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="a6796-128">Создайте ключ для этого приложения.</span><span class="sxs-lookup"><span data-stu-id="a6796-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="a6796-129">Получите токен с помощью приложения с его ключом.</span><span class="sxs-lookup"><span data-stu-id="a6796-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="a6796-130">Используйте токен для доступа к Microsoft Defender для API конечной точки</span><span class="sxs-lookup"><span data-stu-id="a6796-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="a6796-131">Для получения дополнительной информации [см.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="a6796-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="a6796-132">**Контекст пользователя:**</span><span class="sxs-lookup"><span data-stu-id="a6796-132">**User Context:**</span></span> <br>
    <span data-ttu-id="a6796-133">Используется для выполнения действий в API от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="a6796-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="a6796-134">Шаги, которые необходимо предпринять для доступа к API Defender for Endpoint с контекстом приложения:</span><span class="sxs-lookup"><span data-stu-id="a6796-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="a6796-135">Создайте родное приложение AAD.</span><span class="sxs-lookup"><span data-stu-id="a6796-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="a6796-136">Назначьте желаемое разрешение приложению, например,:« Читать оповещения», «Изолировать машины» и т.д.</span><span class="sxs-lookup"><span data-stu-id="a6796-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="a6796-137">Получите токен с помощью приложения с учетными данными пользователя.</span><span class="sxs-lookup"><span data-stu-id="a6796-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="a6796-138">Используйте токен для доступа к Microsoft Defender для API конечной точки</span><span class="sxs-lookup"><span data-stu-id="a6796-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="a6796-139">Для получения дополнительной информации [см.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="a6796-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="a6796-140">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="a6796-140">Related topics</span></span>
- [<span data-ttu-id="a6796-141">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="a6796-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="a6796-142">Доступ к Microsoft Defender для конечной точки с контекстом приложения</span><span class="sxs-lookup"><span data-stu-id="a6796-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="a6796-143">Доступ к Microsoft Defender для конечной точки с контекстом пользователя</span><span class="sxs-lookup"><span data-stu-id="a6796-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
