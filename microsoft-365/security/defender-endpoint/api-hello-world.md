---
title: Hello World для Microsoft Defender для API конечной точки
ms.reviewer: ''
description: Создайте практический вызов API в стиле "Hello world" в API Microsoft Defender for Endpoint.
keywords: apis, поддерживаемый apis, расширенный поиск, запрос, защита microsoft atp, защитник Майкрософт для конечной точки
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
ms.openlocfilehash: 08188acf1209ea2247a0eb09d722ce74c4540254
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939616"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a><span data-ttu-id="74b7c-104">Microsoft Defender для API конечной точки — Hello World</span><span class="sxs-lookup"><span data-stu-id="74b7c-104">Microsoft Defender for Endpoint API - Hello World</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="74b7c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="74b7c-105">**Applies to:**</span></span> 
- [<span data-ttu-id="74b7c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="74b7c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


- <span data-ttu-id="74b7c-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="74b7c-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74b7c-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="74b7c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a><span data-ttu-id="74b7c-109">Получения оповещений с помощью простого сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="74b7c-109">Get Alerts using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="74b7c-110">Сколько времени требуется для этого примера?</span><span class="sxs-lookup"><span data-stu-id="74b7c-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="74b7c-111">Это занимает всего 5 минут в два шага:</span><span class="sxs-lookup"><span data-stu-id="74b7c-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="74b7c-112">Регистрация приложения</span><span class="sxs-lookup"><span data-stu-id="74b7c-112">Application registration</span></span>
- <span data-ttu-id="74b7c-113">Примеры использования: требуется только копирование и вклейка короткого сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="74b7c-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="74b7c-114">Требуется ли разрешение для подключения?</span><span class="sxs-lookup"><span data-stu-id="74b7c-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="74b7c-115">На этапе регистрации приложений  в клиенте Azure Active Directory (Azure AD) должна быть роль глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="74b7c-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="74b7c-116">Шаг 1 . Создание приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="74b7c-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="74b7c-117">Войдите в [Azure с](https://portal.azure.com) **пользователем Глобального администратора.**</span><span class="sxs-lookup"><span data-stu-id="74b7c-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="74b7c-118">Перейдите к **регистрации приложений Azure Active**  >  **Directory**  >  **.**</span><span class="sxs-lookup"><span data-stu-id="74b7c-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Изображение Microsoft Azure и навигация для регистрации приложений](images/atp-azure-new-app2.png)

3. <span data-ttu-id="74b7c-120">В форме регистрации выберите имя приложения и нажмите кнопку **Регистрация**.</span><span class="sxs-lookup"><span data-stu-id="74b7c-120">In the registration form, choose a name for your application and then click **Register**.</span></span>

4. <span data-ttu-id="74b7c-121">Разрешить приложению доступ к Defender для конечной точки и назначить ему **разрешение "Чтение всех оповещений":**</span><span class="sxs-lookup"><span data-stu-id="74b7c-121">Allow your Application to access Defender for Endpoint and assign it **'Read all alerts'** permission:</span></span>

   - <span data-ttu-id="74b7c-122">На странице приложения щелкните **API Permissions**  >  **Add Permissions Add permission** API my organization  >  **uses** > **WindowsDefenderATP** и нажмите **кнопку WindowsDefenderATP**.</span><span class="sxs-lookup"><span data-stu-id="74b7c-122">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and click on **WindowsDefenderATP**.</span></span>

   - <span data-ttu-id="74b7c-123">**Примечание.** WindowsDefenderATP не появляется в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="74b7c-123">**Note**: WindowsDefenderATP does not appear in the original list.</span></span> <span data-ttu-id="74b7c-124">Чтобы увидеть его, необходимо приступить к написанию его имени в текстовом окне.</span><span class="sxs-lookup"><span data-stu-id="74b7c-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![Изображение доступа к API и выбора API1](images/add-permission.png)

   - <span data-ttu-id="74b7c-126">Выберите **разрешения приложения**  >  **Alert.Read.All** > нажмите **кнопку Добавить разрешения**</span><span class="sxs-lookup"><span data-stu-id="74b7c-126">Choose **Application permissions** > **Alert.Read.All** > Click on **Add permissions**</span></span>

   ![Изображение доступа к API и выбора API2](images/application-permissions.png)

   <span data-ttu-id="74b7c-128">**Важное** примечание. Необходимо выбрать соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="74b7c-128">**Important note**: You need to select the relevant permissions.</span></span> <span data-ttu-id="74b7c-129">"Чтение всех оповещений" — это только пример!</span><span class="sxs-lookup"><span data-stu-id="74b7c-129">'Read All Alerts' is only an example!</span></span>

     <span data-ttu-id="74b7c-130">Например,</span><span class="sxs-lookup"><span data-stu-id="74b7c-130">For instance,</span></span>

     - <span data-ttu-id="74b7c-131">Чтобы [запускать расширенные запросы,](run-advanced-query-api.md)выберите разрешение "Запуск расширенных запросов"</span><span class="sxs-lookup"><span data-stu-id="74b7c-131">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
     - <span data-ttu-id="74b7c-132">Чтобы [изолировать машину,](isolate-machine.md)выберите разрешение "Изолировать машину"</span><span class="sxs-lookup"><span data-stu-id="74b7c-132">To [isolate a machine](isolate-machine.md), select 'Isolate machine' permission</span></span>
     - <span data-ttu-id="74b7c-133">Чтобы определить, какое разрешение вам нужно, обратите внимание на раздел **Разрешения** в API, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="74b7c-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="74b7c-134">Щелкните **согласие гранта**</span><span class="sxs-lookup"><span data-stu-id="74b7c-134">Click **Grant consent**</span></span>

    - <span data-ttu-id="74b7c-135">**Примечание.** Каждый раз, когда вы добавляете разрешение, необходимо нажать **на** согласие гранта, чтобы новое разрешение вступает в силу.</span><span class="sxs-lookup"><span data-stu-id="74b7c-135">**Note**: Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

    ![Изображение разрешений гранта](images/grant-consent.png)

6. <span data-ttu-id="74b7c-137">Добавьте секрет в приложение.</span><span class="sxs-lookup"><span data-stu-id="74b7c-137">Add a secret to the application.</span></span>

    - <span data-ttu-id="74b7c-138">Щелкните **сертификаты &,** добавьте описание в секрет и нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="74b7c-138">Click **Certificates & secrets**, add description to the secret and click **Add**.</span></span>

    <span data-ttu-id="74b7c-139">**Важно.** После щелчка Добавить **скопируйте сгенерированную секретную ценность.**</span><span class="sxs-lookup"><span data-stu-id="74b7c-139">**Important**: After click Add, **copy the generated secret value**.</span></span> <span data-ttu-id="74b7c-140">Вы не сможете получить после того, как уйдете!</span><span class="sxs-lookup"><span data-stu-id="74b7c-140">You won't be able to retrieve after you leave!</span></span>

    ![Изображение ключа создания приложения](images/webapp-create-key2.png)

7. <span data-ttu-id="74b7c-142">Запишите свой ИД приложения и его клиента:</span><span class="sxs-lookup"><span data-stu-id="74b7c-142">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="74b7c-143">На странице приложения перейдите в **Обзор и** скопируйте следующее:</span><span class="sxs-lookup"><span data-stu-id="74b7c-143">On your application page, go to **Overview** and copy the following:</span></span>

   ![Изображение созданного id приложения](images/app-and-tenant-ids.png)


<span data-ttu-id="74b7c-145">Договорились!</span><span class="sxs-lookup"><span data-stu-id="74b7c-145">Done!</span></span> <span data-ttu-id="74b7c-146">Вы успешно зарегистрировали приложение!</span><span class="sxs-lookup"><span data-stu-id="74b7c-146">You have successfully registered an application!</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="74b7c-147">Шаг 2 . Получить маркер с помощью Приложения и использовать этот маркер для доступа к API.</span><span class="sxs-lookup"><span data-stu-id="74b7c-147">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="74b7c-148">Скопируйте сценарий ниже в IsE PowerShell или в текстовый редактор и сохраните его как **"Get-Token.ps1"**</span><span class="sxs-lookup"><span data-stu-id="74b7c-148">Copy the script below to PowerShell ISE or to a text editor, and save it as "**Get-Token.ps1**"</span></span>
-   <span data-ttu-id="74b7c-149">Запуск этого скрипта создает маркер и сохраняет его в рабочей папке под именем **"Latest-token.txt".**</span><span class="sxs-lookup"><span data-stu-id="74b7c-149">Running this script will generate a token and will save it in the working folder under the name "**Latest-token.txt**".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

-   <span data-ttu-id="74b7c-150">Проверка санитарии:</span><span class="sxs-lookup"><span data-stu-id="74b7c-150">Sanity Check:</span></span><br>
<span data-ttu-id="74b7c-151">Запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="74b7c-151">Run the script.</span></span><br>
<span data-ttu-id="74b7c-152">В браузере перейдите к: https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="74b7c-152">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="74b7c-153">Скопируйте маркер (содержимое Latest-token.txt файла).</span><span class="sxs-lookup"><span data-stu-id="74b7c-153">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="74b7c-154">Вклейка в верхнем окне.</span><span class="sxs-lookup"><span data-stu-id="74b7c-154">Paste in the top box.</span></span><br>
<span data-ttu-id="74b7c-155">И посмотрите раздел "Роли".</span><span class="sxs-lookup"><span data-stu-id="74b7c-155">Look for the "roles" section.</span></span> <span data-ttu-id="74b7c-156">Найдите роль Alert.Read.All.</span><span class="sxs-lookup"><span data-stu-id="74b7c-156">Find the Alert.Read.All role.</span></span>

![Изображение jwt.ms](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a><span data-ttu-id="74b7c-158">Позволяет получать оповещений!</span><span class="sxs-lookup"><span data-stu-id="74b7c-158">Lets get the Alerts!</span></span>

-   <span data-ttu-id="74b7c-159">Сценарий ниже будет **использоватьGet-Token.ps1** для доступа к API и будет получать последние 48 часов оповещений.</span><span class="sxs-lookup"><span data-stu-id="74b7c-159">The script below will use **Get-Token.ps1** to access the API and will get the past 48 hours Alerts.</span></span>
-   <span data-ttu-id="74b7c-160">Сохраните этот скрипт в той же папке, что и **предыдущий сценарийGet-Token.ps1.**</span><span class="sxs-lookup"><span data-stu-id="74b7c-160">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="74b7c-161">Скрипт создает два файла (json и csv) с данными в той же папке, что и сценарии.</span><span class="sxs-lookup"><span data-stu-id="74b7c-161">The script creates two files (json and csv) with the data in the same folder as the scripts.</span></span>

```
# Returns Alerts created in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")       

# The URL contains the type of query and the time filter we create above
# Read more about other query options and filters at   Https://TBD- add the documentation link
$url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the alerts from the results. 
$alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json and as csv
$outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation 
```

<span data-ttu-id="74b7c-162">Все готово!</span><span class="sxs-lookup"><span data-stu-id="74b7c-162">You’re all done!</span></span> <span data-ttu-id="74b7c-163">Вы только что успешно:</span><span class="sxs-lookup"><span data-stu-id="74b7c-163">You have just successfully:</span></span>
-   <span data-ttu-id="74b7c-164">Создано, зарегистрировано и приложение</span><span class="sxs-lookup"><span data-stu-id="74b7c-164">Created and registered and application</span></span>
-   <span data-ttu-id="74b7c-165">Предоставлено разрешение для этого приложения на чтение оповещений</span><span class="sxs-lookup"><span data-stu-id="74b7c-165">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="74b7c-166">Подключение API</span><span class="sxs-lookup"><span data-stu-id="74b7c-166">Connected the API</span></span>
-   <span data-ttu-id="74b7c-167">Сценарий PowerShell используется для возврата оповещений, созданных за последние 48 часов</span><span class="sxs-lookup"><span data-stu-id="74b7c-167">Used a PowerShell script to return alerts created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="74b7c-168">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="74b7c-168">Related topic</span></span>
- [<span data-ttu-id="74b7c-169">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="74b7c-169">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="74b7c-170">Доступ к Microsoft Defender для конечной точки с контекстом приложений</span><span class="sxs-lookup"><span data-stu-id="74b7c-170">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="74b7c-171">Доступ к Microsoft Defender для конечной точки с пользовательским контекстом</span><span class="sxs-lookup"><span data-stu-id="74b7c-171">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
