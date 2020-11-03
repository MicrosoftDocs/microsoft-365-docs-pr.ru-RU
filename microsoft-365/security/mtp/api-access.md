---
title: Доступ к API-интерфейсам защитника Microsoft 365
description: Узнайте, как получить доступ к API защитника Microsoft 365
keywords: доступ, API, контекст приложения, контекст пользователя, приложение AAD, маркер доступа
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845024"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="01981-104">Доступ к API-интерфейсам защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01981-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01981-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="01981-105">**Applies to:**</span></span>
- <span data-ttu-id="01981-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01981-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="01981-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="01981-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="01981-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="01981-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="01981-109">Защитник Microsoft 365 предоставляет множество своих данных и действий через набор программных интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="01981-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="01981-110">Эти API позволяют автоматизировать рабочие процессы и внедрять их на основе возможностей защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01981-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="01981-111">Для доступа к API требуется проверка подлинности OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="01981-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="01981-112">Для получения дополнительных сведений см [код авторизации OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="01981-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="01981-113">В общем случае необходимо выполнить следующие действия, чтобы использовать API:</span><span class="sxs-lookup"><span data-stu-id="01981-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="01981-114">Создание приложения AAD</span><span class="sxs-lookup"><span data-stu-id="01981-114">Create an AAD application</span></span>
- <span data-ttu-id="01981-115">Получение маркера доступа с помощью этого приложения</span><span class="sxs-lookup"><span data-stu-id="01981-115">Get an access token using this application</span></span>
- <span data-ttu-id="01981-116">Использование маркера для доступа к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01981-116">Use the token to access  Microsoft 365 Defender API</span></span>


<span data-ttu-id="01981-117">Вы можете получить доступ к API защитника Microsoft 365 с **контекстом приложения** или **контекстом пользователя**.</span><span class="sxs-lookup"><span data-stu-id="01981-117">You can access Microsoft 365 Defender API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="01981-118">**Контекст приложения: (рекомендуется)**</span><span class="sxs-lookup"><span data-stu-id="01981-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="01981-119">Используется приложениями, которые запускаются без наличия вошедшего пользователя.</span><span class="sxs-lookup"><span data-stu-id="01981-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="01981-120">Например, приложения, запускаемые как фоновые службы или управляющие программы.</span><span class="sxs-lookup"><span data-stu-id="01981-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="01981-121">Действия, которые необходимо предпринять для доступа к API защитника Microsoft 365 с контекстом приложения:</span><span class="sxs-lookup"><span data-stu-id="01981-121">Steps that need to be taken to access  Microsoft 365 Defender API with application context:</span></span>

  1. <span data-ttu-id="01981-122">Создайте веб-приложение AAD.</span><span class="sxs-lookup"><span data-stu-id="01981-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="01981-123">Назначьте нужное разрешение для примера Аппликатионфор, " **инцидент. Read. ALL** ", **адванцедхунтинг. Read. ALL**.</span><span class="sxs-lookup"><span data-stu-id="01981-123">Assign the desired permission to the applicationFor example, **Incident.Read.All** , **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="01981-124">Создайте ключ для этого приложения.</span><span class="sxs-lookup"><span data-stu-id="01981-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="01981-125">Получение маркера с помощью приложения с ключом.</span><span class="sxs-lookup"><span data-stu-id="01981-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="01981-126">Использование маркера для доступа к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01981-126">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="01981-127">Дополнительные сведения приведены в разделе [Get Access with context](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="01981-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="01981-128">**Контекст пользователя:**</span><span class="sxs-lookup"><span data-stu-id="01981-128">**User Context:**</span></span> <br>
    <span data-ttu-id="01981-129">Используется для выполнения действий в API от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="01981-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="01981-130">Действия, которые необходимо предпринять для доступа к API защитника Microsoft 365 с контекстом приложения:</span><span class="sxs-lookup"><span data-stu-id="01981-130">Steps that needs to be taken to access  Microsoft 365 Defender API with application context:</span></span>
  1. <span data-ttu-id="01981-131">Создание собственного приложения AAD.</span><span class="sxs-lookup"><span data-stu-id="01981-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="01981-132">Назначьте нужное разрешение приложению.</span><span class="sxs-lookup"><span data-stu-id="01981-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="01981-133">Например, " **происшествия. чтение** ", " **адванцедхунтинг. Read** ".</span><span class="sxs-lookup"><span data-stu-id="01981-133">For example, **Incident.Read** , **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="01981-134">Получение маркера с помощью приложения с учетными данными пользователя.</span><span class="sxs-lookup"><span data-stu-id="01981-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="01981-135">Использование маркера для доступа к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01981-135">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="01981-136">Дополнительные сведения можно найти [в разделе Получение доступа с помощью контекста пользователя](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="01981-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="01981-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="01981-137">Related topics</span></span>
- [<span data-ttu-id="01981-138">API-интерфейсы защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01981-138">Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="01981-139">Доступ к защитнику Microsoft 365 с контекстом приложения</span><span class="sxs-lookup"><span data-stu-id="01981-139">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="01981-140">Доступ к защитнику Microsoft 365 с контекстом пользователя</span><span class="sxs-lookup"><span data-stu-id="01981-140">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
