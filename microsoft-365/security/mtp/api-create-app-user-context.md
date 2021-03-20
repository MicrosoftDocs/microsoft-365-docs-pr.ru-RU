---
title: Создание приложения для доступа к API Защитника Microsoft 365 от имени пользователя
description: Узнайте, как получить доступ к API Защитника Microsoft 365 от имени пользователя.
keywords: доступ от имени пользователя, api, приложения, пользователя, маркера доступа, маркера,
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
ms.openlocfilehash: 85c41c0bae9590e76801c18b2a33401874cc7cc3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903956"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="a19b6-104">Создание приложения для доступа к API Защитника Microsoft 365 от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="a19b6-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a19b6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a19b6-105">**Applies to:**</span></span>

- <span data-ttu-id="a19b6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a19b6-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a19b6-107">Некоторые сведения относятся к предварительно изданным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="a19b6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a19b6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="a19b6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a19b6-109">На этой странице описывается создание приложения для получения программного доступа к Microsoft 365 Defender от имени одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a19b6-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="a19b6-110">Если вам необходим программный доступ к Microsoft 365 Defender без определенного пользователя (например, если вы пишете фоновое приложение или daemon), см. в раздел Создание приложения для доступа к [Microsoft 365 Defender](api-create-app-web.md)без пользователя .</span><span class="sxs-lookup"><span data-stu-id="a19b6-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="a19b6-111">Если вам необходимо предоставить доступ для нескольких клиентов, например, если вы обслуживаете крупную организацию или группу клиентов, см. в приложении [Create a app with partner access to Microsoft 365 Defender API.](api-partner-access.md) Если вы не уверены, какой доступ вам нужен, см. [в этой ленте Начало](api-access.md)работы.</span><span class="sxs-lookup"><span data-stu-id="a19b6-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="a19b6-112">Microsoft 365 Defender предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="a19b6-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="a19b6-113">Эти API помогают автоматизировать рабочий процесс и использовать возможности Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a19b6-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="a19b6-114">Этот доступ к API требует проверки подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="a19b6-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="a19b6-115">Дополнительные сведения см. в [тексте OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="a19b6-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="a19b6-116">В общем, для использования этих API необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a19b6-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="a19b6-117">Создание приложения Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a19b6-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="a19b6-118">Получение маркера доступа с помощью этого приложения.</span><span class="sxs-lookup"><span data-stu-id="a19b6-118">Get an access token using this application.</span></span>
- <span data-ttu-id="a19b6-119">Используйте маркер для доступа к API Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a19b6-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="a19b6-120">В этой статье объясняется, как:</span><span class="sxs-lookup"><span data-stu-id="a19b6-120">This article explains how to:</span></span>

- <span data-ttu-id="a19b6-121">Создание приложения Azure AD</span><span class="sxs-lookup"><span data-stu-id="a19b6-121">Create an Azure AD application</span></span>
- <span data-ttu-id="a19b6-122">Получите маркер доступа к Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a19b6-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="a19b6-123">Проверка маркера</span><span class="sxs-lookup"><span data-stu-id="a19b6-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="a19b6-124">При доступе к API Защитника Microsoft 365 от имени пользователя вам потребуется правильные разрешения приложения и разрешения пользователей.</span><span class="sxs-lookup"><span data-stu-id="a19b6-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="a19b6-125">Если у вас есть разрешение на выполнение действия на портале, у вас есть разрешение на выполнение действия в API.</span><span class="sxs-lookup"><span data-stu-id="a19b6-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="a19b6-126">Создать приложение</span><span class="sxs-lookup"><span data-stu-id="a19b6-126">Create an app</span></span>

1. <span data-ttu-id="a19b6-127">Во входе [в Azure](https://portal.azure.com) в качестве пользователя с **ролью глобального администратора.**</span><span class="sxs-lookup"><span data-stu-id="a19b6-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="a19b6-128">Перейдите к **регистрации приложений Azure Active**  >  **Directory**  >  **.**</span><span class="sxs-lookup"><span data-stu-id="a19b6-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Изображение Microsoft Azure и навигация для регистрации приложений](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="a19b6-130">В форме выберите имя приложения и введите следующую информацию для URI перенаправления, а затем **зарегистрируйтесь.**</span><span class="sxs-lookup"><span data-stu-id="a19b6-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Изображение окна создания приложения](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="a19b6-132">**Тип приложения:** Общедоступный клиент</span><span class="sxs-lookup"><span data-stu-id="a19b6-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="a19b6-133">**Перенаправление URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="a19b6-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="a19b6-134">На странице приложения выберите **API Permissions Add**  >  **permission**  >  **API,** которые моя организация использует >, введите Microsoft Threat Protection и выберите **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="a19b6-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="a19b6-135">Теперь ваше приложение может получить доступ к Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a19b6-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="a19b6-136">*Microsoft Threat Protection* — это прежнее имя защитника Microsoft 365, которое не будет отображаться в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="a19b6-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="a19b6-137">Чтобы увидеть его, необходимо приступить к написанию его имени в текстовом окне.</span><span class="sxs-lookup"><span data-stu-id="a19b6-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="a19b6-139">Выберите **делегирование разрешений.**</span><span class="sxs-lookup"><span data-stu-id="a19b6-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="a19b6-140">Выберите соответствующие разрешения для сценария **(например, Incident.Read),** а затем **добавьте разрешения.**</span><span class="sxs-lookup"><span data-stu-id="a19b6-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="a19b6-142">Необходимо выбрать соответствующие разрешения для сценария.</span><span class="sxs-lookup"><span data-stu-id="a19b6-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="a19b6-143">*Чтение всех инцидентов* — это только пример.</span><span class="sxs-lookup"><span data-stu-id="a19b6-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="a19b6-144">Чтобы определить, какое разрешение вам нужно, обратите внимание на раздел **Разрешения** в API, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="a19b6-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="a19b6-145">Например, для [запуска расширенных запросов](api-advanced-hunting.md)выберите разрешение "Запуск расширенных запросов"; чтобы [изолировать устройство,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)выберите разрешение "Изолировать машину".</span><span class="sxs-lookup"><span data-stu-id="a19b6-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="a19b6-146">Выберите **согласие администратора Гранта**.</span><span class="sxs-lookup"><span data-stu-id="a19b6-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="a19b6-147">Каждый раз, когда вы добавляете разрешение, необходимо выбрать согласие администратора **Гранта,** чтобы оно вступает в силу.</span><span class="sxs-lookup"><span data-stu-id="a19b6-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Изображение разрешений гранта](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="a19b6-149">Запись ID приложения и ID клиента в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="a19b6-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="a19b6-150">Они перечислены в статье **Обзор на** странице приложения.</span><span class="sxs-lookup"><span data-stu-id="a19b6-150">They're listed under **Overview** on your application page.</span></span>

   ![Изображение созданного id приложения](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="a19b6-152">Получение токена доступа</span><span class="sxs-lookup"><span data-stu-id="a19b6-152">Get an access token</span></span>

<span data-ttu-id="a19b6-153">Дополнительные сведения о маркерах Azure Active Directory см. в руководстве [Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="a19b6-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="a19b6-154">Получить маркер доступа с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a19b6-154">Get an access token using PowerShell</span></span>

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a><span data-ttu-id="a19b6-155">Проверка маркера</span><span class="sxs-lookup"><span data-stu-id="a19b6-155">Validate the token</span></span>

1. <span data-ttu-id="a19b6-156">Скопируйте и вклейте маркер [в JWT,](https://jwt.ms) чтобы расшифровать его.</span><span class="sxs-lookup"><span data-stu-id="a19b6-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="a19b6-157">Убедитесь, что *утверждение ролей* в расшифроваемом маркере содержит нужные разрешения.</span><span class="sxs-lookup"><span data-stu-id="a19b6-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="a19b6-158">На следующем изображении можно увидеть расшифровав маркер, приобретенный из приложения, с разрешениями и ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` разрешениями:</span><span class="sxs-lookup"><span data-stu-id="a19b6-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Изображение проверки маркеров](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="a19b6-160">Используйте маркер для доступа к API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a19b6-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="a19b6-161">Выберите API, который вы хотите использовать (инциденты или расширенный поиск).</span><span class="sxs-lookup"><span data-stu-id="a19b6-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="a19b6-162">Дополнительные сведения см. в [сайте Supported Microsoft 365 Defender API.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="a19b6-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="a19b6-163">В http-запросе, который вы отправляете, задайте загон авторизации , Bearer является схемой авторизации, а маркер - `"Bearer" <token>` проверенным маркером.  </span><span class="sxs-lookup"><span data-stu-id="a19b6-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="a19b6-164">Срок действия маркера истекает в течение одного часа.</span><span class="sxs-lookup"><span data-stu-id="a19b6-164">The token will expire within one hour.</span></span> <span data-ttu-id="a19b6-165">За это время вы можете отправить несколько запросов с одним маркером.</span><span class="sxs-lookup"><span data-stu-id="a19b6-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="a19b6-166">В следующем примере показано, как отправить запрос для получения списка инцидентов **с C#**.</span><span class="sxs-lookup"><span data-stu-id="a19b6-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="a19b6-167">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a19b6-167">Related articles</span></span>

- [<span data-ttu-id="a19b6-168">Обзор API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a19b6-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="a19b6-169">Доступ к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a19b6-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="a19b6-170">Создание приложения "Hello world"</span><span class="sxs-lookup"><span data-stu-id="a19b6-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="a19b6-171">Создание приложения для доступа к Microsoft 365 Defender без пользователя</span><span class="sxs-lookup"><span data-stu-id="a19b6-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="a19b6-172">Создание приложения с несколькими партнерами-партнерами для API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a19b6-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="a19b6-173">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="a19b6-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="a19b6-174">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="a19b6-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="a19b6-175">Авторизация OAuth 2.0 для входов пользователей и доступа к API</span><span class="sxs-lookup"><span data-stu-id="a19b6-175">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)