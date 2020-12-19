---
title: Hello World для REST API Защитника Microsoft 365
description: Узнайте, как создать приложение и использовать маркер для доступа к API Microsoft 365 Defender
keywords: приложение, маркер, доступ, aad, приложение, регистрация приложения, powershell, сценарий, глобальный администратор, разрешение, Защитник Microsoft 365
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719314"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="f4779-104">Hello World для REST API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4779-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f4779-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f4779-105">**Applies to:**</span></span>

- <span data-ttu-id="f4779-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4779-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4779-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="f4779-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f4779-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f4779-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="f4779-109">Получить инциденты с помощью простого сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4779-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="f4779-110">Этот проект должен занять от 5 до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="f4779-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="f4779-111">В этот раз оценка включает регистрацию приложения и применение кода из примера сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4779-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="f4779-112">Регистрация приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f4779-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="f4779-113">Во sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span><span class="sxs-lookup"><span data-stu-id="f4779-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="f4779-114">Перейдите к регистрации приложений **Azure Active Directory**  >  **— новая**  >  **регистрация.**</span><span class="sxs-lookup"><span data-stu-id="f4779-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Изображение Microsoft Azure и переход к регистрации приложений](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="f4779-116">В форме регистрации выберите имя приложения, а затем выберите **"Регистрация".**</span><span class="sxs-lookup"><span data-stu-id="f4779-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="f4779-117">Выбор URI перенаправления необязателен.</span><span class="sxs-lookup"><span data-stu-id="f4779-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="f4779-118">Для выполнения этого примера он не потребуется.</span><span class="sxs-lookup"><span data-stu-id="f4779-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="f4779-119">На странице приложения выберите "API Разрешения для добавления разрешений" **API,** которые моя организация использует >, введите "Защита от угроз (Майкрософт)" и выберите "Защита от  >    >   **угроз (Майкрософт)".** </span><span class="sxs-lookup"><span data-stu-id="f4779-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="f4779-120">Теперь ваше приложение может получить доступ к Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f4779-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="f4779-121">*Защита от угроз (Майкрософт)* — это прежнее имя Защитника Microsoft 365, которое не будет отображаться в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="f4779-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="f4779-122">Чтобы увидеть, как оно появляется, необходимо начать писать его имя в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="f4779-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="f4779-123">![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="f4779-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="f4779-124">Выберите **разрешения приложения**  >  **Incident.Read.All** и выберите **"Добавить разрешения".**</span><span class="sxs-lookup"><span data-stu-id="f4779-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="f4779-126">Выберите **"Предоставить согласие администратора".**</span><span class="sxs-lookup"><span data-stu-id="f4779-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="f4779-127">При каждом добавлении разрешения  необходимо выбрать разрешение администратора, чтобы оно вступает в силу.</span><span class="sxs-lookup"><span data-stu-id="f4779-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Изображение разрешения на предоставление](../../media/grant-consent.PNG)

6. <span data-ttu-id="f4779-129">Добавьте секрет в приложение.</span><span class="sxs-lookup"><span data-stu-id="f4779-129">Add a secret to the application.</span></span> <span data-ttu-id="f4779-130">Select **Certificates & secrets,** add a description to the secret, then select **Add**.</span><span class="sxs-lookup"><span data-stu-id="f4779-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f4779-131">После выбора **"Добавить"** выберите **"Скопировать сгенерированную секретную копию".**</span><span class="sxs-lookup"><span data-stu-id="f4779-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="f4779-132">После этого вы не сможете получить значение секрета.</span><span class="sxs-lookup"><span data-stu-id="f4779-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Изображение создания ключа приложения](../../media/webapp-create-key2.png)

7. <span data-ttu-id="f4779-134">Зафиксировать свой ИД приложения и ид клиента в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="f4779-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="f4779-135">Они перечислены в **списке "Обзор"** на странице приложения.</span><span class="sxs-lookup"><span data-stu-id="f4779-135">They're listed under **Overview** on your application page.</span></span>

   ![Изображение созданного ид приложения](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="f4779-137">Получите маркер с помощью приложения и используйте его для доступа к API</span><span class="sxs-lookup"><span data-stu-id="f4779-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="f4779-138">Дополнительные сведения о маркерах Azure Active Directory см. в руководстве [по Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="f4779-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4779-139">Несмотря на то, что в примере в этом демонстрационных приложениях  рекомендуется в целях тестирования в paste in your secret value, никогда не следует жестко кодировать секреты в приложение, запущенное в производственной версии.</span><span class="sxs-lookup"><span data-stu-id="f4779-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="f4779-140">Третья сторона может использовать ваш секрет для доступа к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="f4779-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="f4779-141">Вы можете обеспечить безопасность секретов приложения с помощью [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="f4779-141">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="f4779-142">Практический пример того, как можно защитить приложение, см. в под управлением секретов в серверных приложениях [с помощью Azure Key Vault.](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="f4779-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="f4779-143">Скопируйте сценарий ниже и в paste его в избранный текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="f4779-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="f4779-144">Сохраните как **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="f4779-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="f4779-145">Вы также можете запустить код как есть в PowerShell ISE, но его следует сохранить, так как нам потребуется запустить его снова, когда мы будем использовать сценарий получения инцидентов в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="f4779-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="f4779-146">Этот сценарий создает маркер и сохраняет его в рабочей папке под именем *Latest-token.txt.*</span><span class="sxs-lookup"><span data-stu-id="f4779-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

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

#### <a name="validate-the-token"></a><span data-ttu-id="f4779-147">Проверка маркера</span><span class="sxs-lookup"><span data-stu-id="f4779-147">Validate the token</span></span>

1. <span data-ttu-id="f4779-148">Скопируйте и в paste маркер, полученный в [JWT,](https://jwt.ms) чтобы декодировать его.</span><span class="sxs-lookup"><span data-stu-id="f4779-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="f4779-149">*JWT* означает *веб-маркер JSON.*</span><span class="sxs-lookup"><span data-stu-id="f4779-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="f4779-150">Раскодированный маркер будет содержать ряд элементов или утверждений в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="f4779-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="f4779-151">Убедитесь, что *утверждение ролей* внутри раскодирования маркера содержит нужные разрешения.</span><span class="sxs-lookup"><span data-stu-id="f4779-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="f4779-152">На следующем изображении можно увидеть раскодный маркер, полученный из приложения, с ```Incidents.Read.All``` разрешениями ```Incidents.ReadWrite.All``` и ```AdvancedHunting.Read.All``` разрешениями:</span><span class="sxs-lookup"><span data-stu-id="f4779-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Изображение jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="f4779-154">Получить список последних инцидентов</span><span class="sxs-lookup"><span data-stu-id="f4779-154">Get a list of recent incidents</span></span>

<span data-ttu-id="f4779-155">Сценарий ниже **будет** использоватьGet-Token.ps1для доступа к API.</span><span class="sxs-lookup"><span data-stu-id="f4779-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="f4779-156">Затем он извлекает список инцидентов, которые были в последний раз обновлены в течение последних 48 часов, и сохраняет список в JSON-файле.</span><span class="sxs-lookup"><span data-stu-id="f4779-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4779-157">Сохраните этот сценарий в той же папке, в **Get-Token.ps1.**</span><span class="sxs-lookup"><span data-stu-id="f4779-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

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

<span data-ttu-id="f4779-158">Все готово!</span><span class="sxs-lookup"><span data-stu-id="f4779-158">You're all done!</span></span> <span data-ttu-id="f4779-159">Вы успешно выполнили:</span><span class="sxs-lookup"><span data-stu-id="f4779-159">You've successfully:</span></span>

- <span data-ttu-id="f4779-160">Создано и зарегистрировано приложение.</span><span class="sxs-lookup"><span data-stu-id="f4779-160">Created and registered an application.</span></span>
- <span data-ttu-id="f4779-161">Предоставлено разрешение для этого приложения на чтение оповещений.</span><span class="sxs-lookup"><span data-stu-id="f4779-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="f4779-162">Подключен к API.</span><span class="sxs-lookup"><span data-stu-id="f4779-162">Connected to the API.</span></span>
- <span data-ttu-id="f4779-163">Использовал сценарий PowerShell для возврата инцидентов, обновленных за последние 48 часов.</span><span class="sxs-lookup"><span data-stu-id="f4779-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f4779-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f4779-164">Related articles</span></span>

- [<span data-ttu-id="f4779-165">Обзор API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4779-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="f4779-166">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4779-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="f4779-167">Создание приложения для доступа к Microsoft 365 Defender без пользователя</span><span class="sxs-lookup"><span data-stu-id="f4779-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="f4779-168">Создание приложения для доступа к API Microsoft 365 Defender от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="f4779-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="f4779-169">Создание приложения с мультиязычным доступом партнеров к API Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4779-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="f4779-170">Управление секретами в серверных приложениях с помощью Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="f4779-170">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="f4779-171">Авторизация OAuth 2.0 для доступа пользователя к API и входу в нее</span><span class="sxs-lookup"><span data-stu-id="f4779-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
