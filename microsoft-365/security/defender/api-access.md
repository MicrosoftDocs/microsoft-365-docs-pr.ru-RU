---
title: Доступ к API защитника Microsoft 365
description: Узнайте, как получить доступ к API защитника Microsoft 365
keywords: доступ, apis, контекст приложений, пользовательский контекст, aad-приложение, маркер доступа
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1fbba132e664f4773496eac7123a0a408db5b3bd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072758"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="4c716-104">Доступ к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c716-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4c716-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4c716-105">**Applies to:**</span></span>

- <span data-ttu-id="4c716-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c716-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c716-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="4c716-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4c716-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="4c716-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="4c716-109">Microsoft 365 Defender предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="4c716-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="4c716-110">Эти API помогают автоматизировать рабочий процесс и полностью использовать возможности Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4c716-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="4c716-111">В общем, для использования API необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4c716-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="4c716-112">Создание приложения Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4c716-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="4c716-113">Получение маркера доступа с помощью этого приложения</span><span class="sxs-lookup"><span data-stu-id="4c716-113">Get an access token using this application</span></span>
- <span data-ttu-id="4c716-114">Используйте маркер для доступа к API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c716-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="4c716-115">Доступ к API требует проверки подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="4c716-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="4c716-116">Дополнительные сведения см. в [тексте OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="4c716-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="4c716-117">После выполнения этих действий вы будете готовы получить доступ к API защитника Microsoft 365 с помощью определенного контекста.</span><span class="sxs-lookup"><span data-stu-id="4c716-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="4c716-118">Контекст приложения (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="4c716-118">Application context (Recommended)</span></span>

<span data-ttu-id="4c716-119">Используйте этот контекст для приложений, которые работают без участия пользователя, например фоновых служб или daemons.</span><span class="sxs-lookup"><span data-stu-id="4c716-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="4c716-120">Создание веб-приложения Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4c716-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="4c716-121">Назначение нужных разрешений приложению.</span><span class="sxs-lookup"><span data-stu-id="4c716-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="4c716-122">Создайте ключ для приложения.</span><span class="sxs-lookup"><span data-stu-id="4c716-122">Create a key for the application.</span></span>
4. <span data-ttu-id="4c716-123">Получение маркера безопасности с помощью приложения и его ключа.</span><span class="sxs-lookup"><span data-stu-id="4c716-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="4c716-124">Используйте маркер для доступа к API Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c716-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="4c716-125">Дополнительные сведения см. в **[статью Создание приложения для доступа к Microsoft 365 Defender без пользователя.](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="4c716-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="4c716-126">Контекст пользователя</span><span class="sxs-lookup"><span data-stu-id="4c716-126">User context</span></span>

<span data-ttu-id="4c716-127">Используйте этот контекст для выполнения действий от имени одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c716-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="4c716-128">Создание родного приложения Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4c716-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="4c716-129">Назначьте нужное разрешение приложению.</span><span class="sxs-lookup"><span data-stu-id="4c716-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="4c716-130">Получение маркера безопасности с помощью учетных данных пользователя для приложения.</span><span class="sxs-lookup"><span data-stu-id="4c716-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="4c716-131">Используйте маркер для доступа к API Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c716-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="4c716-132">Дополнительные сведения см. в приложении **[Create to access Microsoft 365 Defender API от имени пользователя.](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="4c716-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="4c716-133">Контекст партнеров</span><span class="sxs-lookup"><span data-stu-id="4c716-133">Partner context</span></span>

<span data-ttu-id="4c716-134">Используйте этот контекст, когда необходимо предоставить приложение многим пользователям во [многих клиентах.](/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="4c716-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="4c716-135">Создание мульти-клиентского приложения Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4c716-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="4c716-136">Назначьте нужное разрешение приложению.</span><span class="sxs-lookup"><span data-stu-id="4c716-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="4c716-137">Получите [согласие администратора](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) для приложения от каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="4c716-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="4c716-138">Получите маркер безопасности с помощью учетных данных пользователей на основе удостоверения клиента клиента.</span><span class="sxs-lookup"><span data-stu-id="4c716-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="4c716-139">Используйте маркер для доступа к API Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c716-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="4c716-140">Дополнительные сведения см. в приложении **[Create with partner access to Microsoft 365 Defender API.](api-partner-access.md)**</span><span class="sxs-lookup"><span data-stu-id="4c716-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4c716-141">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="4c716-141">Related articles</span></span>

- [<span data-ttu-id="4c716-142">Обзор API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c716-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="4c716-143">Авторизация OAuth 2.0 для входов пользователей и доступа к API</span><span class="sxs-lookup"><span data-stu-id="4c716-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="4c716-144">Управление секретами в приложениях сервера с помощью хранилища ключей Azure</span><span class="sxs-lookup"><span data-stu-id="4c716-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="4c716-145">Создание приложения "Hello world", которое имеет доступ к API Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c716-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)