---
title: Извлечение оповещений клиента MSSP
description: Узнайте, как получать оповещения от клиента-клиента
keywords: поставщик управляемых служб безопасности, mssp, настройка, интеграция
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770773"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="bf0b3-104">Извлечение оповещений клиента MSSP</span><span class="sxs-lookup"><span data-stu-id="bf0b3-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf0b3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bf0b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf0b3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="bf0b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="bf0b3-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="bf0b3-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bf0b3-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="bf0b3-109">Это действие будет принимать msSP.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="bf0b3-110">Существует два способа получения оповещений:</span><span class="sxs-lookup"><span data-stu-id="bf0b3-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="bf0b3-111">Использование метода SIEM</span><span class="sxs-lookup"><span data-stu-id="bf0b3-111">Using the SIEM method</span></span>
- <span data-ttu-id="bf0b3-112">Использование API</span><span class="sxs-lookup"><span data-stu-id="bf0b3-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="bf0b3-113">Извлечение оповещений в SIEM</span><span class="sxs-lookup"><span data-stu-id="bf0b3-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="bf0b3-114">Для получения оповещений в системе SIEM необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bf0b3-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="bf0b3-115">Шаг 1. Создание сторонних приложений</span><span class="sxs-lookup"><span data-stu-id="bf0b3-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="bf0b3-116">Шаг 2. Получить доступ и обновить маркеры от клиента клиента</span><span class="sxs-lookup"><span data-stu-id="bf0b3-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="bf0b3-117">Шаг 3: разрешить приложение на Центр безопасности в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bf0b3-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="bf0b3-118">Шаг 1. Создание приложения в Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="bf0b3-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="bf0b3-119">Необходимо создать приложение и предоставить ему разрешения на получение оповещений от клиента клиента Microsoft Defender для клиента Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="bf0b3-120">Во входе на [портал Azure AD](https://aad.portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="bf0b3-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="bf0b3-121">Выберите **Azure Active Directory**  >  **регистрации приложений.**</span><span class="sxs-lookup"><span data-stu-id="bf0b3-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="bf0b3-122">Нажмите **кнопку Новая регистрация**.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-122">Click **New registration**.</span></span>

4. <span data-ttu-id="bf0b3-123">Укажите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bf0b3-123">Specify the following values:</span></span>

    - <span data-ttu-id="bf0b3-124">Имя: \<Tenant_name\> соединителем SIEM MSSP (замените Tenant_name на имя отображения клиента)</span><span class="sxs-lookup"><span data-stu-id="bf0b3-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="bf0b3-125">Поддерживаемые типы учетных записей. Учетная запись только в этом организационном каталоге</span><span class="sxs-lookup"><span data-stu-id="bf0b3-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="bf0b3-126">Перенаправление URI: Выберите Веб и введите `https://<domain_name>/SiemMsspConnector` (замените <domain_name> на имя клиента)</span><span class="sxs-lookup"><span data-stu-id="bf0b3-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="bf0b3-127">Нажмите **Зарегистрировать**.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-127">Click **Register**.</span></span> <span data-ttu-id="bf0b3-128">Приложение отображается в списке собственных приложений.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="bf0b3-129">Выберите приложение, а затем щелкните **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="bf0b3-130">Скопируйте значение из поля ID приложения **(клиента)** в безопасное место, это потребуется на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="bf0b3-131">Выберите **& сертификата в** новой панели приложений.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="bf0b3-132">Нажмите **кнопку Новый секрет клиента**.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="bf0b3-133">Описание. Введите описание ключа.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="bf0b3-134">Истекает срок действия: выберите **в 1 год**</span><span class="sxs-lookup"><span data-stu-id="bf0b3-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="bf0b3-135">Нажмите **кнопку Добавить,** скопируйте значение секрета клиента в безопасное место, это потребуется на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="bf0b3-136">Шаг 2. Получить доступ и обновить маркеры от клиента клиента</span><span class="sxs-lookup"><span data-stu-id="bf0b3-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="bf0b3-137">В этом разделе вы можете узнать, как использовать сценарий PowerShell для получения маркеров от клиента.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="bf0b3-138">Этот скрипт использует приложение на предыдущем этапе для получения доступа и обновления маркеров с помощью кода авторизации OAuth Flow.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="bf0b3-139">После предоставления учетных данных необходимо предоставить согласие на приложение, чтобы приложение было задано в клиенте клиента.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="bf0b3-140">Создайте новую папку и назови ее: `MsspTokensAcquisition` .</span><span class="sxs-lookup"><span data-stu-id="bf0b3-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="bf0b3-141">Скачайте [модуль LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) и сохраните его в `MsspTokensAcquisition` папке.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="bf0b3-142">В строке 30 замените `authorzationUrl` `authorizationUrl` .</span><span class="sxs-lookup"><span data-stu-id="bf0b3-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="bf0b3-143">Создайте файл со следующим содержимым и сохраните его с именем `MsspTokensAcquisition.ps1` в папке:</span><span class="sxs-lookup"><span data-stu-id="bf0b3-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="bf0b3-144">Откройте командную подсказку PowerShell повышенной мощности в `MsspTokensAcquisition` папке.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="bf0b3-145">Выполните следующую команду: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="bf0b3-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="bf0b3-146">Введите следующие команды: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="bf0b3-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="bf0b3-147">\<client_id\>Замените **ID приложения (клиента),** который вы получили на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="bf0b3-148">Замените \<app_key\> секрет **клиента,** созданный на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="bf0b3-149">Замените \<customer_tenant_id\> с клиентом **tenant ID**.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="bf0b3-150">Вам будет предложено предоставить учетные данные и согласие.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="bf0b3-151">Игнорировать перенаправление страницы.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="bf0b3-152">В окне PowerShell вы получите маркер доступа и маркер обновления.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="bf0b3-153">Сохраните маркер обновления, чтобы настроить соединитель SIEM.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="bf0b3-154">Шаг 3. Разрешить применение в Центр безопасности в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bf0b3-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="bf0b3-155">Необходимо разрешить приложение, созданное в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="bf0b3-156">Чтобы разрешить приложение, необходимо иметь разрешение **на** управление настройками системы портала.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="bf0b3-157">В противном случае необходимо попросить клиента разрешить приложение для вас.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="bf0b3-158">Перейдите `https://securitycenter.windows.com?tid=<customer_tenant_id>` к \<customer_tenant_id\> (замените его ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="bf0b3-159">Щелкните **Параметры**  >  **SIEM**.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="bf0b3-160">Выберите **вкладку MSSP.**</span><span class="sxs-lookup"><span data-stu-id="bf0b3-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="bf0b3-161">Введите **ID приложения** с первого шага и ваш **ID клиента**.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="bf0b3-162">Нажмите **кнопку Авторизировать приложение**.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="bf0b3-163">Теперь можно скачать соответствующий файл конфигурации для SIEM и подключиться к API Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="bf0b3-164">Дополнительные сведения см. в дополнительных сведениях о том, как вывести [оповещения в инструменты SIEM.](configure-siem.md)</span><span class="sxs-lookup"><span data-stu-id="bf0b3-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="bf0b3-165">В файле свойств конфигурации ArcSight / Splunk Authentication Properties напишите ключ приложения вручную, задав секретное значение.</span><span class="sxs-lookup"><span data-stu-id="bf0b3-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="bf0b3-166">Вместо приобретения маркера обновления на портале используйте скрипт предыдущего шага, чтобы приобрести маркер обновления (или приобрести его другими средствами).</span><span class="sxs-lookup"><span data-stu-id="bf0b3-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="bf0b3-167">Извлечение оповещений клиента MSSP с помощью API</span><span class="sxs-lookup"><span data-stu-id="bf0b3-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="bf0b3-168">Сведения о том, как получать оповещения с помощью API REST, см. в руб. в руб. [Pull alerts using REST API.](pull-alerts-using-rest-api.md)</span><span class="sxs-lookup"><span data-stu-id="bf0b3-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="bf0b3-169">См. также</span><span class="sxs-lookup"><span data-stu-id="bf0b3-169">See also</span></span>
- [<span data-ttu-id="bf0b3-170">Предоставление MSSP доступа к порталу</span><span class="sxs-lookup"><span data-stu-id="bf0b3-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="bf0b3-171">Получение доступа к порталу клиентов MSSP</span><span class="sxs-lookup"><span data-stu-id="bf0b3-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="bf0b3-172">Настройка уведомлений оповещений</span><span class="sxs-lookup"><span data-stu-id="bf0b3-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
