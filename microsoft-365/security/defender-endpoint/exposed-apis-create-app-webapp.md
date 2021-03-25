---
title: Создание приложения для доступа к Microsoft Defender для конечной точки без пользователя
ms.reviewer: ''
description: Узнайте, как создать веб-приложение, чтобы получить программный доступ к Microsoft Defender для конечной точки без пользователя.
keywords: apis, api graph, supported apis, actor, alerts, device, user, domain, ip, file, advanced hunting, query
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8f480a148d72428c6346930a91358d1e8b674ee7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200009"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a><span data-ttu-id="76536-104">Создание приложения для доступа к Microsoft Defender для конечной точки без пользователя</span><span class="sxs-lookup"><span data-stu-id="76536-104">Create an app to access Microsoft Defender for Endpoint without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="76536-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="76536-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="76536-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="76536-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76536-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="76536-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="76536-108">На этой странице описывается создание приложения для получения программного доступа к Защитнику для конечной точки без пользователя.</span><span class="sxs-lookup"><span data-stu-id="76536-108">This page describes how to create an application to get programmatic access to Defender for Endpoint without a user.</span></span> <span data-ttu-id="76536-109">Если вам необходим программный доступ к Защитнику для конечной точки от имени пользователя, см. раздел Получить доступ [с пользовательским контекстом.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="76536-109">If you need programmatic access to Defender for Endpoint on behalf of a user, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span> <span data-ttu-id="76536-110">Если вы не уверены, какой доступ вам нужен, см. [в этой ленте Начало](apis-intro.md)работы.</span><span class="sxs-lookup"><span data-stu-id="76536-110">If you are not sure which access you need, see [Get started](apis-intro.md).</span></span>

<span data-ttu-id="76536-111">Microsoft Defender для конечной точки предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="76536-111">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="76536-112">Эти API помогут автоматизировать потоки работы и вносимые новации на основе возможностей Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="76536-112">Those APIs will help you automate work flows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="76536-113">Доступ к API требует проверки подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="76536-113">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="76536-114">Дополнительные сведения см. в [тексте OAuth 2.0 Authorization Code Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="76536-114">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="76536-115">В общем, для использования API необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="76536-115">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="76536-116">Создание приложения Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="76536-116">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="76536-117">Получение маркера доступа с помощью этого приложения.</span><span class="sxs-lookup"><span data-stu-id="76536-117">Get an access token using this application.</span></span>
- <span data-ttu-id="76536-118">Используйте маркер для доступа к API Defender для endpoint.</span><span class="sxs-lookup"><span data-stu-id="76536-118">Use the token to access Defender for Endpoint API.</span></span>

<span data-ttu-id="76536-119">В этой статье рассказывается о создании приложения Azure AD, предоставлении маркера доступа в Microsoft Defender для конечной точки и проверке маркера.</span><span class="sxs-lookup"><span data-stu-id="76536-119">This article explains how to create an Azure AD application, get an access token to Microsoft Defender for Endpoint, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="76536-120">Создать приложение</span><span class="sxs-lookup"><span data-stu-id="76536-120">Create an app</span></span>

1. <span data-ttu-id="76536-121">Войдите в [Azure](https://portal.azure.com) с пользователем, который имеет роль **глобального администратора.**</span><span class="sxs-lookup"><span data-stu-id="76536-121">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="76536-122">Перейдите к **регистрации приложений Azure Active**  >  **Directory**  >  **.**</span><span class="sxs-lookup"><span data-stu-id="76536-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Изображение Microsoft Azure и навигация для регистрации приложений](images/atp-azure-new-app2.png)

3. <span data-ttu-id="76536-124">В форме регистрации выберите имя приложения, а затем выберите **Register**.</span><span class="sxs-lookup"><span data-stu-id="76536-124">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="76536-125">Чтобы включить приложение для доступа к Defender для конечной точки и назначить ему разрешение "Чтение всех оповещений", выберите **API** **Permissions** Add  >  **permissionS** my  >  **organization uses** >, введите **WindowsDefenderATP,** а затем выберите **WindowsDefenderATP**.</span><span class="sxs-lookup"><span data-stu-id="76536-125">To enable your app to access Defender for Endpoint and assign it **'Read all alerts'** permission, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **WindowsDefenderATP**, and then select **WindowsDefenderATP**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="76536-126">*WindowsDefenderATP* не появляется в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="76536-126">*WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="76536-127">Начните писать свое имя в текстовом окне, чтобы увидеть его.</span><span class="sxs-lookup"><span data-stu-id="76536-127">Start writing its name in the text box to see it appear.</span></span>

   ![добавление разрешений](images/add-permission.png)

   - <span data-ttu-id="76536-129">Выберите **разрешения приложения**  >  **Alert.Read.All,** а затем добавьте **разрешения.**</span><span class="sxs-lookup"><span data-stu-id="76536-129">Select **Application permissions** > **Alert.Read.All**, and then select **Add permissions**.</span></span>

   ![Разрешение приложения](images/application-permissions.png)

     <span data-ttu-id="76536-131">Необходимо выбрать соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="76536-131">You need to select the relevant permissions.</span></span> <span data-ttu-id="76536-132">"Чтение всех оповещений" — это только пример.</span><span class="sxs-lookup"><span data-stu-id="76536-132">'Read All Alerts' is only an example.</span></span> <span data-ttu-id="76536-133">Например:</span><span class="sxs-lookup"><span data-stu-id="76536-133">For instance:</span></span>

     - <span data-ttu-id="76536-134">Чтобы [запустить расширенные запросы,](run-advanced-query-api.md)выберите разрешение "Выполнить расширенные запросы".</span><span class="sxs-lookup"><span data-stu-id="76536-134">To [run advanced queries](run-advanced-query-api.md), select the 'Run advanced queries' permission.</span></span>
     - <span data-ttu-id="76536-135">Чтобы [изолировать устройство,](isolate-machine.md)выберите разрешение "Изолировать машину".</span><span class="sxs-lookup"><span data-stu-id="76536-135">To [isolate a device](isolate-machine.md), select the 'Isolate machine' permission.</span></span>
     - <span data-ttu-id="76536-136">Чтобы определить, какое разрешение вам нужно, посмотрите раздел **Разрешения** в API, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="76536-136">To determine which permission you need, look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="76536-137">Выберите **согласие гранта.**</span><span class="sxs-lookup"><span data-stu-id="76536-137">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="76536-138">Каждый раз, когда вы добавляете разрешение, необходимо выбрать согласие **гранта,** чтобы новое разрешение вступает в силу.</span><span class="sxs-lookup"><span data-stu-id="76536-138">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![Предоставление разрешений](images/grant-consent.png)

6. <span data-ttu-id="76536-140">Чтобы добавить секрет в приложение, выберите сертификаты **&,** добавьте описание в секрет, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="76536-140">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="76536-141">После выбора **Добавить** выберите **скопируйте сгенерированную секретную ценность.**</span><span class="sxs-lookup"><span data-stu-id="76536-141">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="76536-142">Вы не сможете получить это значение после того, как уйдете.</span><span class="sxs-lookup"><span data-stu-id="76536-142">You won't be able to retrieve this value after you leave.</span></span>

    ![Изображение ключа создания приложения](images/webapp-create-key2.png)

7. <span data-ttu-id="76536-144">Запишите свой ИД приложения и его клиента.</span><span class="sxs-lookup"><span data-stu-id="76536-144">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="76536-145">На странице приложения перейдите к **обзору и** скопируйте следующее.</span><span class="sxs-lookup"><span data-stu-id="76536-145">On your application page, go to **Overview** and copy the following.</span></span>

   ![Изображение созданного id приложения](images/app-and-tenant-ids.png)

8. <span data-ttu-id="76536-147">**Только для Microsoft Defender для партнеров конечных точек**.</span><span class="sxs-lookup"><span data-stu-id="76536-147">**For Microsoft Defender for Endpoint Partners only**.</span></span> <span data-ttu-id="76536-148">Задайте вашему приложению много клиента (доступное во всех клиентах после согласия).</span><span class="sxs-lookup"><span data-stu-id="76536-148">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="76536-149">Это необходимо **для** сторонних приложений (например, если вы создаете приложение, предназначенное для работы в клиенте нескольких клиентов).</span><span class="sxs-lookup"><span data-stu-id="76536-149">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="76536-150">Это не **требуется,** если вы создаете службу, которую нужно запустить только в клиенте (например, если вы создаете приложение для собственного использования, которое будет взаимодействовать только с собственными данными).</span><span class="sxs-lookup"><span data-stu-id="76536-150">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="76536-151">Чтобы установить, что ваше приложение является многонанимателем:</span><span class="sxs-lookup"><span data-stu-id="76536-151">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="76536-152">Перейдите **к проверке подлинности** и добавьте `https://portal.azure.com` в качестве **URI перенаправления.**</span><span class="sxs-lookup"><span data-stu-id="76536-152">Go to **Authentication**, and add `https://portal.azure.com` as the **Redirect URI**.</span></span>

    - <span data-ttu-id="76536-153">В нижней части страницы в рамках поддерживаемых типов учетных записей выберите учетные записи в любом приложении-каталоге организации для вашего приложения с несколькими клиентами. </span><span class="sxs-lookup"><span data-stu-id="76536-153">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="76536-154">Необходимо, чтобы ваше приложение было утверждено в каждом клиенте, где вы собираетесь его использовать.</span><span class="sxs-lookup"><span data-stu-id="76536-154">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="76536-155">Это происходит потому, что приложение взаимодействует с Defender для конечной точки от имени клиента.</span><span class="sxs-lookup"><span data-stu-id="76536-155">This is because your application interacts Defender for Endpoint on behalf of your customer.</span></span>

    <span data-ttu-id="76536-156">Вам (или вашему клиенту, если вы пишете сторонное приложение) необходимо выбрать ссылку на согласие и утвердить ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="76536-156">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="76536-157">Согласие должно быть сделано с пользователем, у которого есть административные привилегии в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="76536-157">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="76536-158">Ссылка согласия формируется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="76536-158">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="76536-159">Где 00000000-0000-0000-0000-0000000000000 заменяется вашим ИД приложения.</span><span class="sxs-lookup"><span data-stu-id="76536-159">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="76536-160">**Договорились!**</span><span class="sxs-lookup"><span data-stu-id="76536-160">**Done!**</span></span> <span data-ttu-id="76536-161">Вы успешно зарегистрировали приложение!</span><span class="sxs-lookup"><span data-stu-id="76536-161">You have successfully registered an application!</span></span> <span data-ttu-id="76536-162">Ниже приведены примеры приобретения и проверки маркеров.</span><span class="sxs-lookup"><span data-stu-id="76536-162">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="76536-163">Получение токена доступа</span><span class="sxs-lookup"><span data-stu-id="76536-163">Get an access token</span></span>

<span data-ttu-id="76536-164">Дополнительные сведения о маркерах Azure AD см. в руководстве [Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="76536-164">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="76536-165">Воспользуйтесь PowerShell</span><span class="sxs-lookup"><span data-stu-id="76536-165">Use PowerShell</span></span>

```powershell
# This script acquires the App Context Token and stores it in the variable $token for later use in the script.
# Paste your Tenant ID, App ID, and App Secret (App key) into the indicated quotes below.

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
```

### <a name="use-c"></a><span data-ttu-id="76536-166">Используйте C#:</span><span class="sxs-lookup"><span data-stu-id="76536-166">Use C#:</span></span>

<span data-ttu-id="76536-167">Следующий код был протестирован с помощью NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="76536-167">The following code was tested with NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="76536-168">Создайте новое консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="76536-168">Create a new console application.</span></span>
1. <span data-ttu-id="76536-169">Установка NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="76536-169">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="76536-170">Добавьте следующее:</span><span class="sxs-lookup"><span data-stu-id="76536-170">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="76536-171">Скопируйте и вклейте следующий код в приложении (не забудьте обновить три переменные: ```tenantId, appId, appSecret``` ):</span><span class="sxs-lookup"><span data-stu-id="76536-171">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.microsoftonline.com";
    const string wdatpResourceId = "https://api.securitycenter.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="76536-172">Использование Python</span><span class="sxs-lookup"><span data-stu-id="76536-172">Use Python</span></span>

<span data-ttu-id="76536-173">См. [маркер Get using Python.](run-advanced-query-sample-python.md#get-token)</span><span class="sxs-lookup"><span data-stu-id="76536-173">See [Get token using Python](run-advanced-query-sample-python.md#get-token).</span></span>

### <a name="use-curl"></a><span data-ttu-id="76536-174">Использование Curl</span><span class="sxs-lookup"><span data-stu-id="76536-174">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="76536-175">Следующая процедура предполагает, что curl для Windows уже установлен на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="76536-175">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="76536-176">Откройте командную подсказку и установите CLIENT_ID к вашему ID приложения Azure.</span><span class="sxs-lookup"><span data-stu-id="76536-176">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="76536-177">Установите CLIENT_SECRET для секрета приложения Azure.</span><span class="sxs-lookup"><span data-stu-id="76536-177">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="76536-178">Установите TENANT_ID для клиента Azure, который хочет использовать приложение для доступа к Защитнику для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="76536-178">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Defender for Endpoint.</span></span>
1. <span data-ttu-id="76536-179">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="76536-179">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="76536-180">Вы получите ответ в следующей форме:</span><span class="sxs-lookup"><span data-stu-id="76536-180">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="76536-181">Проверка маркера</span><span class="sxs-lookup"><span data-stu-id="76536-181">Validate the token</span></span>

<span data-ttu-id="76536-182">Убедитесь, что вы получили правильный маркер:</span><span class="sxs-lookup"><span data-stu-id="76536-182">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="76536-183">Скопируйте и вклейте маркер, который вы получили на предыдущем шаге в [JWT,](https://jwt.ms) чтобы расшифровать его.</span><span class="sxs-lookup"><span data-stu-id="76536-183">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="76536-184">Проверка получения утверждения "роли" с нужными разрешениями</span><span class="sxs-lookup"><span data-stu-id="76536-184">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="76536-185">На следующем изображении можно увидеть расшифровав маркер, приобретенный из приложения с разрешениями на все роли Microsoft Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="76536-185">In the following image, you can see a decoded token acquired from an app with permissions to all of  Microsoft Defender for Endpoint's roles:</span></span>

![Изображение проверки маркеров](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="76536-187">С помощью маркера можно получить доступ к API Endpoint Defender для Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="76536-187">Use the token to access Microsoft Defender for Endpoint API</span></span>

1. <span data-ttu-id="76536-188">Выберите API, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="76536-188">Choose the API you want to use.</span></span> <span data-ttu-id="76536-189">Дополнительные сведения см. в [ссылке Supported Defender for Endpoint API.](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="76536-189">For more information, see [Supported Defender for Endpoint APIs](exposed-apis-list.md).</span></span>
1. <span data-ttu-id="76536-190">Установите заглавную запись авторизации в http-запросе, который вы отправляете в "Bearer {token}" (Bearer — это схема авторизации).</span><span class="sxs-lookup"><span data-stu-id="76536-190">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>
1. <span data-ttu-id="76536-191">Срок действия маркера — один час.</span><span class="sxs-lookup"><span data-stu-id="76536-191">The expiration time of the token is one hour.</span></span> <span data-ttu-id="76536-192">Вы можете отправить несколько запросов с одним и тем же маркером.</span><span class="sxs-lookup"><span data-stu-id="76536-192">You can send more than one request with the same token.</span></span>

<span data-ttu-id="76536-193">Ниже приводится пример отправки запроса для получения списка оповещений **с помощью C#:**</span><span class="sxs-lookup"><span data-stu-id="76536-193">The following is an example of sending a request to get a list of alerts **using C#**:</span></span> 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a><span data-ttu-id="76536-194">См. также</span><span class="sxs-lookup"><span data-stu-id="76536-194">See also</span></span>
- [<span data-ttu-id="76536-195">Поддерживаемые API-API Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="76536-195">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="76536-196">Доступ к Microsoft Defender для конечной точки от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="76536-196">Access Microsoft Defender for Endpoint on behalf of a user</span></span>](exposed-apis-create-app-nativeapp.md)
