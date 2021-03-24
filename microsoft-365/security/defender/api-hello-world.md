---
title: Hello World for Microsoft 365 Defender REST API
description: Узнайте, как создать приложение и использовать маркер для доступа к API Защитника Microsoft 365
keywords: app, token, access, aad, app, application registration, powershell, script, global administrator, permission, Microsoft 365 defender
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
ms.openlocfilehash: ffdcf91da6b5def7d63e5fdb8ff51ddbdb1ec550
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072757"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="bd408-104">Hello World for Microsoft 365 Defender REST API</span><span class="sxs-lookup"><span data-stu-id="bd408-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bd408-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bd408-105">**Applies to:**</span></span>

- <span data-ttu-id="bd408-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd408-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd408-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="bd408-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bd408-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="bd408-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="bd408-109">Получать инциденты с помощью простого сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd408-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="bd408-110">На завершение этого проекта должно пройти от 5 до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="bd408-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="bd408-111">Эта оценка времени включает регистрацию приложения и применение кода из сценария образца PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd408-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="bd408-112">Регистрация приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bd408-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="bd408-113">Во входе [в Azure](https://portal.azure.com) в качестве пользователя с **ролью глобального администратора.**</span><span class="sxs-lookup"><span data-stu-id="bd408-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="bd408-114">Перейдите к **регистрации приложений Azure Active**  >  **Directory**  >  **.**</span><span class="sxs-lookup"><span data-stu-id="bd408-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Изображение Microsoft Azure и навигация для регистрации приложений](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="bd408-116">В форме регистрации выберите имя приложения, а затем выберите **Register**.</span><span class="sxs-lookup"><span data-stu-id="bd408-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="bd408-117">Выбор URI перенаправления необязателен.</span><span class="sxs-lookup"><span data-stu-id="bd408-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="bd408-118">Для завершения этого примера не потребуется один пример.</span><span class="sxs-lookup"><span data-stu-id="bd408-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="bd408-119">На странице приложения выберите **API Permissions Add**  >  **permission**  >  **API,** которые моя организация использует >, введите Microsoft Threat Protection и выберите **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="bd408-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="bd408-120">Теперь ваше приложение может получить доступ к Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bd408-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="bd408-121">*Microsoft Threat Protection* — это прежнее имя защитника Microsoft 365, которое не будет отображаться в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="bd408-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="bd408-122">Чтобы увидеть его, необходимо приступить к написанию его имени в текстовом окне.</span><span class="sxs-lookup"><span data-stu-id="bd408-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="bd408-123">![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="bd408-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="bd408-124">Выберите **разрешения приложения**  >  **Incident.Read.All** и добавьте **разрешения.**</span><span class="sxs-lookup"><span data-stu-id="bd408-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="bd408-126">Выберите **согласие администратора Гранта**.</span><span class="sxs-lookup"><span data-stu-id="bd408-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="bd408-127">Каждый раз, когда вы добавляете разрешение, необходимо выбрать согласие администратора **Гранта,** чтобы оно вступает в силу.</span><span class="sxs-lookup"><span data-stu-id="bd408-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Изображение разрешений гранта](../../media/grant-consent.PNG)

6. <span data-ttu-id="bd408-129">Добавьте секрет в приложение.</span><span class="sxs-lookup"><span data-stu-id="bd408-129">Add a secret to the application.</span></span> <span data-ttu-id="bd408-130">Выберите **сертификаты &,** добавьте описание в секрет, а затем **добавьте**.</span><span class="sxs-lookup"><span data-stu-id="bd408-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="bd408-131">После выбора **Добавить** выберите **скопируйте сгенерированную секретную ценность.**</span><span class="sxs-lookup"><span data-stu-id="bd408-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="bd408-132">Вы не сможете получить секретное значение после того, как вы уйдете.</span><span class="sxs-lookup"><span data-stu-id="bd408-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Изображение ключа создания приложения](../../media/webapp-create-key2.png)

7. <span data-ttu-id="bd408-134">Запись ID приложения и ID клиента в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="bd408-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="bd408-135">Они перечислены в статье **Обзор на** странице приложения.</span><span class="sxs-lookup"><span data-stu-id="bd408-135">They're listed under **Overview** on your application page.</span></span>

   ![Изображение созданного id приложения](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="bd408-137">Получите маркер с помощью приложения и используйте маркер для доступа к API</span><span class="sxs-lookup"><span data-stu-id="bd408-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="bd408-138">Дополнительные сведения о маркерах Azure Active Directory см. в руководстве [Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="bd408-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd408-139">Хотя в примере в этом демо-приложении рекомендуется вклеить  секретное значение для целей тестирования, никогда не следует секретов жесткого кода в приложение, запущенное в производстве.</span><span class="sxs-lookup"><span data-stu-id="bd408-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="bd408-140">Третья сторона может использовать ваш секрет для доступа к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="bd408-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="bd408-141">Вы можете помочь сохранить секреты вашего приложения в безопасности с помощью [Хранилища ключей Azure.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="bd408-141">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="bd408-142">Пример того, как защитить приложение, см. в примере Управление секретами в серверных приложениях [с помощью хранилища ключей Azure.](/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="bd408-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="bd408-143">Скопируйте сценарий ниже и вклейте его в любимый текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="bd408-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="bd408-144">Сохраните как **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="bd408-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="bd408-145">Вы также можете запустить код как есть в ISE PowerShell, но его следует сохранить, так как нам потребуется выполнить его снова, когда мы используем сценарий для получения инцидентов в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="bd408-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="bd408-146">Этот скрипт будет создавать маркер и сохранять его в рабочей папке под именем *Latest-token.txt*.</span><span class="sxs-lookup"><span data-stu-id="bd408-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a><span data-ttu-id="bd408-147">Проверка маркера</span><span class="sxs-lookup"><span data-stu-id="bd408-147">Validate the token</span></span>

1. <span data-ttu-id="bd408-148">Скопируйте и вклейте маркер, полученный в [JWT,](https://jwt.ms) чтобы расшифровать его.</span><span class="sxs-lookup"><span data-stu-id="bd408-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="bd408-149">*JWT* — это *веб-маркер JSON.*</span><span class="sxs-lookup"><span data-stu-id="bd408-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="bd408-150">Декодированный маркер будет содержать ряд элементов или утверждений в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="bd408-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="bd408-151">Убедитесь, что *утверждение ролей* в расшифроваемом маркере содержит нужные разрешения.</span><span class="sxs-lookup"><span data-stu-id="bd408-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="bd408-152">На следующем изображении можно увидеть расшифровав маркер, приобретенный из приложения, с разрешениями и ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` разрешениями:</span><span class="sxs-lookup"><span data-stu-id="bd408-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Изображение jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="bd408-154">Получить список последних инцидентов</span><span class="sxs-lookup"><span data-stu-id="bd408-154">Get a list of recent incidents</span></span>

<span data-ttu-id="bd408-155">Сценарий ниже будет использовать **Get-Token.ps1** для доступа к API.</span><span class="sxs-lookup"><span data-stu-id="bd408-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="bd408-156">Затем он извлекает список инцидентов, которые были обновлены в течение последних 48 часов, и сохраняет список в качестве JSON-файла.</span><span class="sxs-lookup"><span data-stu-id="bd408-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd408-157">Сохраните этот скрипт в той же папке, что и **Get-Token.ps1.**</span><span class="sxs-lookup"><span data-stu-id="bd408-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

<span data-ttu-id="bd408-158">Все готово!</span><span class="sxs-lookup"><span data-stu-id="bd408-158">You're all done!</span></span> <span data-ttu-id="bd408-159">Вы успешно:</span><span class="sxs-lookup"><span data-stu-id="bd408-159">You've successfully:</span></span>

- <span data-ttu-id="bd408-160">Создано и зарегистрировано приложение.</span><span class="sxs-lookup"><span data-stu-id="bd408-160">Created and registered an application.</span></span>
- <span data-ttu-id="bd408-161">Предоставлено разрешение для этого приложения на чтение оповещений.</span><span class="sxs-lookup"><span data-stu-id="bd408-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="bd408-162">Подключение к API.</span><span class="sxs-lookup"><span data-stu-id="bd408-162">Connected to the API.</span></span>
- <span data-ttu-id="bd408-163">Для возврата инцидентов, обновленных за последние 48 часов, используется скрипт PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd408-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bd408-164">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="bd408-164">Related articles</span></span>

- [<span data-ttu-id="bd408-165">Обзор API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd408-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="bd408-166">Доступ к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd408-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="bd408-167">Создание приложения для доступа к Microsoft 365 Defender без пользователя</span><span class="sxs-lookup"><span data-stu-id="bd408-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="bd408-168">Создание приложения для доступа к API Защитника Microsoft 365 от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="bd408-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="bd408-169">Создание приложения с несколькими партнерами-партнерами для API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd408-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="bd408-170">Управление секретами в приложениях сервера с помощью хранилища ключей Azure</span><span class="sxs-lookup"><span data-stu-id="bd408-170">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="bd408-171">OAuth 2.0 Авторизация для входов пользователей и доступа к API</span><span class="sxs-lookup"><span data-stu-id="bd408-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)