---
title: Доступ к API защиты от угроз Майкрософт
description: Узнайте, как получить доступ к API защиты от угроз Майкрософт
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
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650512"
---
# <a name="access-the-microsoft-threat-protection-apis"></a><span data-ttu-id="f162c-104">Доступ к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f162c-104">Access the Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="f162c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f162c-105">**Applies to:**</span></span>
- <span data-ttu-id="f162c-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f162c-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="f162c-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="f162c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f162c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f162c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="f162c-109">Защита от угроз Майкрософт предоставляет множество своих данных и действий через набор программных интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="f162c-109">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="f162c-110">Эти API позволяют автоматизировать рабочие процессы и внедрять их на основе возможностей защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f162c-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="f162c-111">Для доступа к API требуется проверка подлинности OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="f162c-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="f162c-112">Для получения дополнительных сведений см [код авторизации OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="f162c-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="f162c-113">В общем случае необходимо выполнить следующие действия, чтобы использовать API:</span><span class="sxs-lookup"><span data-stu-id="f162c-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="f162c-114">Создание приложения AAD</span><span class="sxs-lookup"><span data-stu-id="f162c-114">Create an AAD application</span></span>
- <span data-ttu-id="f162c-115">Получение маркера доступа с помощью этого приложения</span><span class="sxs-lookup"><span data-stu-id="f162c-115">Get an access token using this application</span></span>
- <span data-ttu-id="f162c-116">Использование маркера для доступа к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f162c-116">Use the token to access  Microsoft Threat Protection API</span></span>


<span data-ttu-id="f162c-117">Доступ к API Microsoft Threat Protection можно получить с помощью **контекста приложения** или **контекста пользователя**.</span><span class="sxs-lookup"><span data-stu-id="f162c-117">You can access  Microsoft Threat Protection API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="f162c-118">**Контекст приложения: (рекомендуется)**</span><span class="sxs-lookup"><span data-stu-id="f162c-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="f162c-119">Используется приложениями, которые запускаются без наличия вошедшего пользователя.</span><span class="sxs-lookup"><span data-stu-id="f162c-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="f162c-120">Например, приложения, запускаемые как фоновые службы или управляющие программы.</span><span class="sxs-lookup"><span data-stu-id="f162c-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="f162c-121">Действия, которые необходимо предпринять для доступа к API Microsoft Threat protection с контекстом приложения:</span><span class="sxs-lookup"><span data-stu-id="f162c-121">Steps that need to be taken to access  Microsoft Threat Protection API with application context:</span></span>

  1. <span data-ttu-id="f162c-122">Создайте веб-приложение AAD.</span><span class="sxs-lookup"><span data-stu-id="f162c-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="f162c-123">Назначьте нужное разрешение для примера Аппликатионфор, " **инцидент. Read. ALL**", **адванцедхунтинг. Read. ALL**.</span><span class="sxs-lookup"><span data-stu-id="f162c-123">Assign the desired permission to the applicationFor example, **Incident.Read.All**, **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="f162c-124">Создайте ключ для этого приложения.</span><span class="sxs-lookup"><span data-stu-id="f162c-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="f162c-125">Получение маркера с помощью приложения с ключом.</span><span class="sxs-lookup"><span data-stu-id="f162c-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="f162c-126">Использование маркера для доступа к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f162c-126">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="f162c-127">Дополнительные сведения приведены в разделе [Get Access with context](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="f162c-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="f162c-128">**Контекст пользователя:**</span><span class="sxs-lookup"><span data-stu-id="f162c-128">**User Context:**</span></span> <br>
    <span data-ttu-id="f162c-129">Используется для выполнения действий в API от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="f162c-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="f162c-130">Действия, которые необходимо предпринять для доступа к API Microsoft Threat protection с контекстом приложения:</span><span class="sxs-lookup"><span data-stu-id="f162c-130">Steps that needs to be taken to access  Microsoft Threat Protection API with application context:</span></span>
  1. <span data-ttu-id="f162c-131">Создание собственного приложения AAD.</span><span class="sxs-lookup"><span data-stu-id="f162c-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="f162c-132">Назначьте нужное разрешение приложению.</span><span class="sxs-lookup"><span data-stu-id="f162c-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="f162c-133">Например, " **происшествия. чтение**", " **адванцедхунтинг. Read**".</span><span class="sxs-lookup"><span data-stu-id="f162c-133">For example, **Incident.Read**, **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="f162c-134">Получение маркера с помощью приложения с учетными данными пользователя.</span><span class="sxs-lookup"><span data-stu-id="f162c-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="f162c-135">Использование маркера для доступа к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f162c-135">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="f162c-136">Дополнительные сведения можно найти [в разделе Получение доступа с помощью контекста пользователя](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="f162c-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="f162c-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f162c-137">Related topics</span></span>
- [<span data-ttu-id="f162c-138">API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f162c-138">Microsoft Threat Protection APIs</span></span>](api-supported.md)
- [<span data-ttu-id="f162c-139">Доступ к защите от угроз Майкрософт с помощью контекста приложения</span><span class="sxs-lookup"><span data-stu-id="f162c-139">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="f162c-140">Доступ к защите от угроз Майкрософт с помощью контекста пользователя</span><span class="sxs-lookup"><span data-stu-id="f162c-140">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
