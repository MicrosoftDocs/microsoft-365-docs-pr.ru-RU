---
title: Доступ к API Microsoft 365 Defender
description: Узнайте, как получить доступ к API Microsoft 365 Defender
keywords: доступ, API, контекст приложения, контекст пользователя, приложение aad, маркер доступа
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932158"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="62736-104">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62736-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="62736-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="62736-105">**Applies to:**</span></span>

- <span data-ttu-id="62736-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62736-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62736-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="62736-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="62736-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="62736-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="62736-109">Защитник Microsoft 365 предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="62736-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="62736-110">Эти API помогают автоматизировать процессы и в полной мере использовать возможности Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62736-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="62736-111">В общем, для использования API необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="62736-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="62736-112">Создание приложения Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="62736-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="62736-113">Получение маркера доступа с помощью этого приложения</span><span class="sxs-lookup"><span data-stu-id="62736-113">Get an access token using this application</span></span>
- <span data-ttu-id="62736-114">Использование маркера для доступа к API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62736-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="62736-115">Для доступа к API требуется проверка подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="62736-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="62736-116">Дополнительные сведения см. в потоке кода авторизации [OAuth 2.0.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="62736-116">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="62736-117">После выполнения этих действий вы можете получить доступ к API Защитника Microsoft 365 с использованием определенного контекста.</span><span class="sxs-lookup"><span data-stu-id="62736-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="62736-118">Контекст приложения (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="62736-118">Application context (Recommended)</span></span>

<span data-ttu-id="62736-119">Используйте этот контекст для приложений, которые работают без выписаного пользователя, например фоновых служб или мям.</span><span class="sxs-lookup"><span data-stu-id="62736-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="62736-120">Создайте веб-приложение Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="62736-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="62736-121">Назначьте приложению нужные разрешения.</span><span class="sxs-lookup"><span data-stu-id="62736-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="62736-122">Создайте ключ для приложения.</span><span class="sxs-lookup"><span data-stu-id="62736-122">Create a key for the application.</span></span>
4. <span data-ttu-id="62736-123">Получение маркера безопасности с помощью приложения и его ключа.</span><span class="sxs-lookup"><span data-stu-id="62736-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="62736-124">Используйте маркер для доступа к API Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62736-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="62736-125">Дополнительные сведения см. в **[теме "Создание приложения для доступа к Защитнику Microsoft 365 без пользователя".](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="62736-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="62736-126">Контекст пользователя</span><span class="sxs-lookup"><span data-stu-id="62736-126">User context</span></span>

<span data-ttu-id="62736-127">Используйте этот контекст для выполнения действий от имени одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="62736-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="62736-128">Создайте приложение Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="62736-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="62736-129">Назначьте приложению нужное разрешение.</span><span class="sxs-lookup"><span data-stu-id="62736-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="62736-130">Получение маркера безопасности с использованием учетных данных пользователя для приложения.</span><span class="sxs-lookup"><span data-stu-id="62736-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="62736-131">Используйте маркер для доступа к API Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62736-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="62736-132">Дополнительные сведения см. в записи "Создание приложения для доступа к API Защитника **[Microsoft 365 от имени пользователя".](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="62736-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="62736-133">Контекст партнера</span><span class="sxs-lookup"><span data-stu-id="62736-133">Partner context</span></span>

<span data-ttu-id="62736-134">Используйте этот контекст, если вам нужно предоставить приложение множеству пользователей в [нескольких клиентах.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="62736-134">Use this context when you need to provide an app to many users across [multiple tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="62736-135">Создайте мультиантивное приложение Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="62736-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="62736-136">Назначьте приложению нужное разрешение.</span><span class="sxs-lookup"><span data-stu-id="62736-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="62736-137">Получите [согласие администратора](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) для приложения от каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="62736-137">Get [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="62736-138">Получите маркер безопасности, используя учетные данные пользователя на основе ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="62736-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="62736-139">Используйте маркер для доступа к API Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62736-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="62736-140">Дополнительные сведения см. в записи "Создание приложения с партнерским **[доступом к API Защитника Microsoft 365".](api-partner-access.md)**</span><span class="sxs-lookup"><span data-stu-id="62736-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="62736-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="62736-141">Related articles</span></span>

- [<span data-ttu-id="62736-142">Обзор API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62736-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="62736-143">Авторизация OAuth 2.0 для доступа пользователя к API и входу в нее</span><span class="sxs-lookup"><span data-stu-id="62736-143">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="62736-144">Управление секретами в серверных приложениях с помощью Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="62736-144">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="62736-145">Создание приложения "Hello world", которое имеет доступ к API Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62736-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
