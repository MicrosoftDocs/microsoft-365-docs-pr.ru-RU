---
title: Создание приложения для доступа Microsoft 365 Defender без пользователя
description: Узнайте, как создать приложение для доступа Microsoft 365 Defender без пользователя.
keywords: приложение, доступ, API, создание
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
ms.openlocfilehash: 8ffa04492f42f7e1ee5f3fc7fadad963e6bb7fbe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074797"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="711a3-104">Создание приложения для доступа Microsoft 365 Defender без пользователя</span><span class="sxs-lookup"><span data-stu-id="711a3-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="711a3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="711a3-105">**Applies to:**</span></span>

- <span data-ttu-id="711a3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="711a3-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="711a3-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="711a3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="711a3-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="711a3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="711a3-109">На этой странице описывается создание приложения для получения программного доступа к Microsoft 365 Defender без определенного пользователя, например, если вы создаете деймон или фоновую службу.</span><span class="sxs-lookup"><span data-stu-id="711a3-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="711a3-110">Если вам необходим программный доступ к Microsoft 365 Defender от имени одного или более пользователей, см. в раздел Создание приложения для доступа к API [Microsoft 365 Defender](api-create-app-user-context.md) от имени пользователя и создание приложения с партнерским доступом к API [Microsoft 365 Defender](api-partner-access.md).</span><span class="sxs-lookup"><span data-stu-id="711a3-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="711a3-111">Если вы не уверены, какой доступ вам нужен, см. [в этой ленте Начало](api-access.md)работы.</span><span class="sxs-lookup"><span data-stu-id="711a3-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="711a3-112">Microsoft 365 Defender предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="711a3-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="711a3-113">Эти API помогают автоматизировать рабочий процесс и использовать возможности Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="711a3-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="711a3-114">Этот доступ к API требует проверки подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="711a3-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="711a3-115">Дополнительные сведения см. [в тексте OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="711a3-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="711a3-116">В общем, для использования этих API необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="711a3-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="711a3-117">Создание приложения Azure Active Directory Azure AD.</span><span class="sxs-lookup"><span data-stu-id="711a3-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="711a3-118">Получение маркера доступа с помощью этого приложения.</span><span class="sxs-lookup"><span data-stu-id="711a3-118">Get an access token using this application.</span></span>
- <span data-ttu-id="711a3-119">Используйте маркер для доступа к API Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="711a3-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="711a3-120">В этой статье объясняется, как:</span><span class="sxs-lookup"><span data-stu-id="711a3-120">This article explains how to:</span></span>

- <span data-ttu-id="711a3-121">Создание приложения Azure AD</span><span class="sxs-lookup"><span data-stu-id="711a3-121">Create an Azure AD application</span></span>
- <span data-ttu-id="711a3-122">Получите маркер доступа к Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="711a3-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="711a3-123">Проверка маркера.</span><span class="sxs-lookup"><span data-stu-id="711a3-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="711a3-124">Создать приложение</span><span class="sxs-lookup"><span data-stu-id="711a3-124">Create an app</span></span>

1. <span data-ttu-id="711a3-125">Во входе [в Azure](https://portal.azure.com) в качестве пользователя с **ролью глобального администратора.**</span><span class="sxs-lookup"><span data-stu-id="711a3-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="711a3-126">Перейдите **к Azure Active Directory**  >  **регистрации Приложений** Новая  >  **регистрация**.</span><span class="sxs-lookup"><span data-stu-id="711a3-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Изображение Microsoft Azure и навигации для регистрации приложений](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="711a3-128">В форме выберите имя приложения, а затем выберите **Register**.</span><span class="sxs-lookup"><span data-stu-id="711a3-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="711a3-129">На странице приложения выберите **API Permissions** Add permission API, которые моя организация использует  >    >   >, **введите** Защита от угроз (Майкрософт) и выберите **Защита от угроз (Майкрософт)**.</span><span class="sxs-lookup"><span data-stu-id="711a3-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="711a3-130">Теперь приложение может получить доступ к Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="711a3-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="711a3-131">*Защита от угроз (Майкрософт)* является прежним именем Microsoft 365 Defender и не будет отображаться в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="711a3-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="711a3-132">Чтобы увидеть его, необходимо приступить к написанию его имени в текстовом окне.</span><span class="sxs-lookup"><span data-stu-id="711a3-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="711a3-134">Выберите **разрешения приложения.**</span><span class="sxs-lookup"><span data-stu-id="711a3-134">Select **Application permissions**.</span></span> <span data-ttu-id="711a3-135">Выберите соответствующие разрешения для сценария (например, **Incident.Read.All),** а затем добавьте **разрешения.**</span><span class="sxs-lookup"><span data-stu-id="711a3-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="711a3-137">Необходимо выбрать соответствующие разрешения для сценария.</span><span class="sxs-lookup"><span data-stu-id="711a3-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="711a3-138">*Чтение всех инцидентов* — это только пример.</span><span class="sxs-lookup"><span data-stu-id="711a3-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="711a3-139">Чтобы определить, какое разрешение вам нужно, обратите внимание на раздел **Разрешения** в API, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="711a3-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="711a3-140">Например, для [запуска расширенных запросов](api-advanced-hunting.md)выберите разрешение "Запуск расширенных запросов"; чтобы [изолировать устройство,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)выберите разрешение "Изолировать машину".</span><span class="sxs-lookup"><span data-stu-id="711a3-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="711a3-141">Выберите **согласие администратора Гранта**.</span><span class="sxs-lookup"><span data-stu-id="711a3-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="711a3-142">Каждый раз, когда вы добавляете разрешение, необходимо выбрать согласие администратора **Гранта,** чтобы оно вступает в силу.</span><span class="sxs-lookup"><span data-stu-id="711a3-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Изображение разрешений гранта](../../media/grant-consent.PNG)

7. <span data-ttu-id="711a3-144">Чтобы добавить секрет в приложение, выберите сертификаты **&,** добавьте описание в секрет, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="711a3-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="711a3-145">После выбора **Добавить** выберите **скопируйте сгенерированную секретную ценность.**</span><span class="sxs-lookup"><span data-stu-id="711a3-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="711a3-146">Вы не сможете получить секретное значение после того, как вы уйдете.</span><span class="sxs-lookup"><span data-stu-id="711a3-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Изображение ключа создания приложения](../../media/webapp-create-key2.png)

8. <span data-ttu-id="711a3-148">Запись ID приложения и ID клиента в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="711a3-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="711a3-149">Они перечислены в статье **Обзор на** странице приложения.</span><span class="sxs-lookup"><span data-stu-id="711a3-149">They're listed under **Overview** on your application page.</span></span>

   ![Изображение созданного id приложения](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="711a3-151">**Для Microsoft 365 только для партнеров Defender:** Следуйте этим инструкциям для доступа партнеров через API Microsoft 365 Defender, установите приложение как многозанимательное, поэтому оно может быть доступно всем арендаторам после получения согласия администратора. [](./api-partner-access.md)</span><span class="sxs-lookup"><span data-stu-id="711a3-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](./api-partner-access.md) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="711a3-152">Доступ партнеров **необходим для** сторонних приложений, например, если вы создаете приложение, предназначенное для работы с несколькими клиентами.</span><span class="sxs-lookup"><span data-stu-id="711a3-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="711a3-153">Это не **обязательно,** если вы создаете службу, которую вы хотите запустить только в клиенте, например приложение для собственного использования, которое будет взаимодействовать только с собственными данными.</span><span class="sxs-lookup"><span data-stu-id="711a3-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="711a3-154">Чтобы установить, что ваше приложение является нескольким клиентом:</span><span class="sxs-lookup"><span data-stu-id="711a3-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="711a3-155">Перейдите **к проверке подлинности** и добавьте https://portal.azure.com в качестве **URI перенаправления.**</span><span class="sxs-lookup"><span data-stu-id="711a3-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="711a3-156">В нижней части страницы в рамках поддерживаемых типов учетных записей выберите учетные записи в любом приложении-каталоге организации для вашего приложения с несколькими клиентами. </span><span class="sxs-lookup"><span data-stu-id="711a3-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="711a3-157">Так как приложение взаимодействует с Microsoft 365 Defender от имени пользователей, оно должно быть утверждено для каждого клиента, на котором вы собираетесь его использовать.</span><span class="sxs-lookup"><span data-stu-id="711a3-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="711a3-158">Глобальный администратор Active Directory для каждого клиента должен выбрать ссылку согласия и утвердить ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="711a3-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="711a3-159">Ссылка согласия имеет следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="711a3-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="711a3-160">Цифры `00000000-0000-0000-0000-000000000000` должны быть заменены на код приложения.</span><span class="sxs-lookup"><span data-stu-id="711a3-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="711a3-161">**Договорились!**</span><span class="sxs-lookup"><span data-stu-id="711a3-161">**Done!**</span></span> <span data-ttu-id="711a3-162">Вы успешно зарегистрировали приложение!</span><span class="sxs-lookup"><span data-stu-id="711a3-162">You've successfully registered an application!</span></span> <span data-ttu-id="711a3-163">Ниже приведены примеры приобретения и проверки маркеров.</span><span class="sxs-lookup"><span data-stu-id="711a3-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="711a3-164">Получение токена доступа</span><span class="sxs-lookup"><span data-stu-id="711a3-164">Get an access token</span></span>

<span data-ttu-id="711a3-165">Дополнительные сведения о маркерах Azure Active Directory см. в руководстве [Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="711a3-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="711a3-166">Хотя в примерах этого раздела рекомендуется вклеить секретные значения  для целей тестирования, никогда не следует секретов жесткого кода в приложение, запущенное в производстве.</span><span class="sxs-lookup"><span data-stu-id="711a3-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="711a3-167">Третья сторона может использовать ваш секрет для доступа к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="711a3-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="711a3-168">Вы можете помочь сохранить секреты вашего приложения в безопасности с помощью [Хранилища ключей Azure.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="711a3-168">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="711a3-169">Пример того, как защитить приложение, см. в примере Управление секретами в серверных приложениях [с помощью хранилища ключей Azure.](/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="711a3-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="711a3-170">Получить маркер доступа с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="711a3-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="711a3-171">Получить маркер доступа с помощью C\#</span><span class="sxs-lookup"><span data-stu-id="711a3-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="711a3-172">Следующий код был протестирован с помощью Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="711a3-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="711a3-173">Создайте новое консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="711a3-173">Create a new console application.</span></span>

1. <span data-ttu-id="711a3-174">Установка NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="711a3-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="711a3-175">Добавьте следующую строку:</span><span class="sxs-lookup"><span data-stu-id="711a3-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="711a3-176">Скопируйте и вклейте в приложение следующий код (не забудьте обновить три переменные: `tenantId` `clientId` , , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="711a3-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="711a3-177">Получить маркер доступа с помощью Python</span><span class="sxs-lookup"><span data-stu-id="711a3-177">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="711a3-178">Получить маркер доступа с помощью завитка</span><span class="sxs-lookup"><span data-stu-id="711a3-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="711a3-179">Curl предварительно установлен на Windows 10 версии 1803 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="711a3-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="711a3-180">Для других версий Windows скачайте и установите средство непосредственно с [официального веб-сайта curl.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="711a3-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="711a3-181">Откройте командную подсказку и установите CLIENT_ID к вашему ID приложения Azure.</span><span class="sxs-lookup"><span data-stu-id="711a3-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="711a3-182">Установите CLIENT_SECRET для секрета приложения Azure.</span><span class="sxs-lookup"><span data-stu-id="711a3-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="711a3-183">Установите TENANT_ID для клиента Azure, который хочет использовать приложение для доступа к Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="711a3-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="711a3-184">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="711a3-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="711a3-185">Успешный ответ будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="711a3-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="711a3-186">Проверка маркера</span><span class="sxs-lookup"><span data-stu-id="711a3-186">Validate the token</span></span>

1. <span data-ttu-id="711a3-187">Скопируйте и вклеите маркер на веб-сайт валидатора веб-маркеров [JSON JWT,](https://jwt.ms) чтобы расшифровать его.</span><span class="sxs-lookup"><span data-stu-id="711a3-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="711a3-188">Убедитесь, что *утверждение ролей* в расшифроваемом маркере содержит нужные разрешения.</span><span class="sxs-lookup"><span data-stu-id="711a3-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="711a3-189">На следующем изображении можно увидеть расшифровав маркер, приобретенный из приложения, с разрешениями и `Incidents.Read.All` `Incidents.ReadWrite.All` `AdvancedHunting.Read.All` разрешениями:</span><span class="sxs-lookup"><span data-stu-id="711a3-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![Изображение проверки маркеров](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="711a3-191">Используйте маркер для доступа к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="711a3-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="711a3-192">Выберите API, который вы хотите использовать (инциденты или расширенный поиск).</span><span class="sxs-lookup"><span data-stu-id="711a3-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="711a3-193">Дополнительные сведения см. в [Microsoft 365 API Defender.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="711a3-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="711a3-194">В http-запросе, который вы должны отправить, установите загон авторизации , Bearer является схемой авторизации, а маркер — `"Bearer" <token>` проверенным маркером.  </span><span class="sxs-lookup"><span data-stu-id="711a3-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="711a3-195">Срок действия маркера истекает в течение одного часа.</span><span class="sxs-lookup"><span data-stu-id="711a3-195">The token will expire within one hour.</span></span> <span data-ttu-id="711a3-196">За это время вы можете отправить несколько запросов с одним маркером.</span><span class="sxs-lookup"><span data-stu-id="711a3-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="711a3-197">В следующем примере показано, как отправить запрос для получения списка инцидентов **с C#**.</span><span class="sxs-lookup"><span data-stu-id="711a3-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="711a3-198">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="711a3-198">Related articles</span></span>

- [<span data-ttu-id="711a3-199">Microsoft 365 Обзор API defender</span><span class="sxs-lookup"><span data-stu-id="711a3-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="711a3-200">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="711a3-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="711a3-201">Создание приложения "Hello world"</span><span class="sxs-lookup"><span data-stu-id="711a3-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="711a3-202">Создание приложения для доступа Microsoft 365 API Defender от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="711a3-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="711a3-203">Создание приложения с несколькими партнерами-партнерами для доступа Microsoft 365 API Defender</span><span class="sxs-lookup"><span data-stu-id="711a3-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="711a3-204">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="711a3-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="711a3-205">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="711a3-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="711a3-206">Управление секретами в приложениях сервера с помощью хранилища ключей Azure</span><span class="sxs-lookup"><span data-stu-id="711a3-206">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="711a3-207">Авторизация OAuth 2.0 для входов пользователей и доступа к API</span><span class="sxs-lookup"><span data-stu-id="711a3-207">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)