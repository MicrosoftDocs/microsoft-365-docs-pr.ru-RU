---
title: Hello World для REST API защитника Microsoft 365
description: Узнайте, как создать приложение и использовать маркер для доступа к API-интерфейсам защитника Microsoft 365.
keywords: приложение, маркер, доступ, AAD, App, регистрация приложений, PowerShell, сценарий, глобальный администратор, разрешение
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
ms.openlocfilehash: bd4f7e5485d67cf74477900ae2cc5c77f1a6ee41
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844048"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="9e051-104">Hello World для REST API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e051-104">Hello World for Microsoft 365 Defender REST API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e051-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9e051-105">**Applies to:**</span></span>
- <span data-ttu-id="9e051-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e051-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="9e051-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="9e051-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9e051-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="9e051-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="9e051-109">Получение инцидентов с помощью простого скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e051-109">Get incidents using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="9e051-110">Сколько времени потребуется проделать через этот пример?</span><span class="sxs-lookup"><span data-stu-id="9e051-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="9e051-111">Выполнение выполняется в течение 5 минут в два этапа:</span><span class="sxs-lookup"><span data-stu-id="9e051-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="9e051-112">Регистрация приложения</span><span class="sxs-lookup"><span data-stu-id="9e051-112">Application registration</span></span>
- <span data-ttu-id="9e051-113">Примеры: требуется только копирование и вставка короткого скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e051-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="9e051-114">Требуется ли разрешение на подключение?</span><span class="sxs-lookup"><span data-stu-id="9e051-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="9e051-115">Для этапа регистрации приложений необходимо иметь роль **глобального администратора** в клиенте Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9e051-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="9e051-116">Шаг 1: создание приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9e051-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="9e051-117">Войдите в [Azure](https://portal.azure.com) с помощью учетной записи **глобального администратора** .</span><span class="sxs-lookup"><span data-stu-id="9e051-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="9e051-118">Перейдите к разделу Регистрация приложений **Azure Active Directory** с  >  **App registrations**  >  **новой регистрацией**.</span><span class="sxs-lookup"><span data-stu-id="9e051-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Изображение Microsoft Azure и переход к регистрации приложения](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="9e051-120">В форме регистрации выберите имя приложения и нажмите кнопку **зарегистрировать**.</span><span class="sxs-lookup"><span data-stu-id="9e051-120">In the registration form, choose a name for your application and then select **Register**.</span></span>

4. <span data-ttu-id="9e051-121">Разрешите приложению получить доступ к защитнику Майкрософт для конечной точки и назначить ему разрешение " **чтение всех происшествий** ":</span><span class="sxs-lookup"><span data-stu-id="9e051-121">Allow your Application to access Microsoft Defender for Endpoint and assign it **Read all incidents** permission:</span></span>

   - <span data-ttu-id="9e051-122">На странице приложение выберите **разрешения API**  >  **Добавление разрешений**  >  **API "Моя организация использует** > введите **Microsoft 365 защитник** и выберите **защитник Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="9e051-122">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft 365 Defender** and select on **Microsoft 365 Defender**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="9e051-123">Защитник Microsoft 365 не отображается в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="9e051-123">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="9e051-124">Чтобы отобразить его имя, необходимо сначала начать его ввод в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="9e051-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![Изображение доступа к API и выбора API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="9e051-126">Выберите **разрешения для приложений**  >  **происшествие инцидент. Read. ALL** > SELECT for **Permissions Permissions**</span><span class="sxs-lookup"><span data-stu-id="9e051-126">Choose **Application permissions** > **Incident.Read.All** > Select on **Add permissions**</span></span>

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   ><span data-ttu-id="9e051-128">Необходимо выбрать соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="9e051-128">You need to select the relevant permissions.</span></span> 

     <span data-ttu-id="9e051-129">Например,</span><span class="sxs-lookup"><span data-stu-id="9e051-129">For instance,</span></span>

     - <span data-ttu-id="9e051-130">Чтобы определить, какое разрешение необходимо, просмотрите раздел **разрешения** в API, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="9e051-130">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="9e051-131">Выбор **предоставления согласия администратора**</span><span class="sxs-lookup"><span data-stu-id="9e051-131">Select **Grant admin consent**</span></span>

    - >[!NOTE]
      > <span data-ttu-id="9e051-132">Каждый раз, когда вы добавляете разрешение, для вступления в силу нового разрешения необходимо выбрать разрешение на **предоставление** разрешения.</span><span class="sxs-lookup"><span data-stu-id="9e051-132">Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

    ![Изображение разрешений GRANT](../../media/grant-consent.PNG)

6. <span data-ttu-id="9e051-134">Добавьте секрет в приложение.</span><span class="sxs-lookup"><span data-stu-id="9e051-134">Add a secret to the application.</span></span>

    - <span data-ttu-id="9e051-135">Выберите **сертификаты & секреты** , добавьте описание к секрету и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9e051-135">Select **Certificates & secrets** , add description to the secret and select **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="9e051-136">После нажатия кнопки **Добавить** **скопируйте созданное значение секрета**.</span><span class="sxs-lookup"><span data-stu-id="9e051-136">After selecting **Add** , **copy the generated secret value**.</span></span> <span data-ttu-id="9e051-137">Вы не сможете получить его после выхода из!</span><span class="sxs-lookup"><span data-stu-id="9e051-137">You won't be able to retrieve after you leave!</span></span>

    ![Изображение ключа "создать приложение"](../../media/webapp-create-key2.png)

7. <span data-ttu-id="9e051-139">Запишите идентификатор своего приложения и идентификатор клиента:</span><span class="sxs-lookup"><span data-stu-id="9e051-139">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="9e051-140">На странице приложения перейдите в раздел **Overview (обзор** ) и скопируйте следующее:</span><span class="sxs-lookup"><span data-stu-id="9e051-140">On your application page, go to **Overview** and copy the following:</span></span>

   ![Изображение идентификатора созданного приложения](../../media/app-and-tenant-ids.png)


<span data-ttu-id="9e051-142">Договорились!</span><span class="sxs-lookup"><span data-stu-id="9e051-142">Done!</span></span> <span data-ttu-id="9e051-143">Вы успешно зарегистрировали приложение.</span><span class="sxs-lookup"><span data-stu-id="9e051-143">You have successfully registered an application.</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="9e051-144">Шаг 2. Получите маркер с помощью приложения и используйте этот маркер для доступа к API.</span><span class="sxs-lookup"><span data-stu-id="9e051-144">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="9e051-145">Скопируйте приведенный ниже скрипт в PowerShell ISE или в текстовый редактор и сохраните его как " **Get-Token.ps1** ".</span><span class="sxs-lookup"><span data-stu-id="9e051-145">Copy the script below to PowerShell ISE or to a text editor, and save it as " **Get-Token.ps1** "</span></span>
-   <span data-ttu-id="9e051-146">При выполнении этого скрипта будет создан маркер, который будет сохранен в рабочей папке под именем " **Latest-token.txt** ".</span><span class="sxs-lookup"><span data-stu-id="9e051-146">Running this script will generate a token and will save it in the working folder under the name " **Latest-token.txt** ".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
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

-   <span data-ttu-id="9e051-147">Проверка санити:</span><span class="sxs-lookup"><span data-stu-id="9e051-147">Sanity Check:</span></span><br>
<span data-ttu-id="9e051-148">Запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="9e051-148">Run the script.</span></span><br>
<span data-ttu-id="9e051-149">В браузере перейдите по адресу: https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="9e051-149">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="9e051-150">Скопируйте маркер (содержимое файла Latest-token.txt).</span><span class="sxs-lookup"><span data-stu-id="9e051-150">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="9e051-151">Вставьте в верхнее поле.</span><span class="sxs-lookup"><span data-stu-id="9e051-151">Paste in the top box.</span></span><br>
<span data-ttu-id="9e051-152">Найдите раздел "роли".</span><span class="sxs-lookup"><span data-stu-id="9e051-152">Look for the "roles" section.</span></span> <span data-ttu-id="9e051-153">Найдите ```Incidents.Read.All``` роль.</span><span class="sxs-lookup"><span data-stu-id="9e051-153">Find the ```Incidents.Read.All``` role.</span></span><br>
<span data-ttu-id="9e051-154">Ниже приведен пример из приложения с ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` разрешениями и разрешениями.</span><span class="sxs-lookup"><span data-stu-id="9e051-154">The below example is from an app that has ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions.</span></span>

![Jwt.ms изображений](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a><span data-ttu-id="9e051-156">Позволяет получить инциденты!</span><span class="sxs-lookup"><span data-stu-id="9e051-156">Lets get the Incidents!</span></span>

-   <span data-ttu-id="9e051-157">Приведенный ниже скрипт будет использовать **Get-Token.ps1** для доступа к API и будет получать последние обновленные происшествия за последние 48 часов.</span><span class="sxs-lookup"><span data-stu-id="9e051-157">The script below will use **Get-Token.ps1** to access the API and will get the incidents last updated in past 48 hours.</span></span>
-   <span data-ttu-id="9e051-158">Сохраните этот скрипт в той же папке, в которой вы сохранили предыдущий **Get-Token.ps1** сценария.</span><span class="sxs-lookup"><span data-stu-id="9e051-158">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="9e051-159">Сценарий — файл JSON с данными в той же папке, что и скрипты.</span><span class="sxs-lookup"><span data-stu-id="9e051-159">The script a json file with the data in the same folder as the scripts.</span></span>

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

<span data-ttu-id="9e051-160">Все готово.</span><span class="sxs-lookup"><span data-stu-id="9e051-160">You're all done!</span></span> <span data-ttu-id="9e051-161">Вы только что успешно:</span><span class="sxs-lookup"><span data-stu-id="9e051-161">You have just successfully:</span></span>
-   <span data-ttu-id="9e051-162">Создано, зарегистрировано и приложение</span><span class="sxs-lookup"><span data-stu-id="9e051-162">Created and registered and application</span></span>
-   <span data-ttu-id="9e051-163">Разрешение на чтение оповещений для этого приложения</span><span class="sxs-lookup"><span data-stu-id="9e051-163">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="9e051-164">Подключен API</span><span class="sxs-lookup"><span data-stu-id="9e051-164">Connected the API</span></span>
-   <span data-ttu-id="9e051-165">Использование скрипта PowerShell для возврата инцидентов, созданных за прошедшие 48 часов</span><span class="sxs-lookup"><span data-stu-id="9e051-165">Used a PowerShell script to return incidents created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="9e051-166">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="9e051-166">Related topic</span></span>
- [<span data-ttu-id="9e051-167">Доступ к API-интерфейсам защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e051-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="9e051-168">Доступ к защитнику Microsoft 365 с контекстом приложения</span><span class="sxs-lookup"><span data-stu-id="9e051-168">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="9e051-169">Доступ к защитнику Microsoft 365 с контекстом пользователя</span><span class="sxs-lookup"><span data-stu-id="9e051-169">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
