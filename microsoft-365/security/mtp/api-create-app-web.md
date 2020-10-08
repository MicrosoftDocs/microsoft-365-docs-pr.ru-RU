---
title: Создание приложения для доступа к защите от угроз Майкрософт без пользователя
description: Узнайте, как создать приложение для доступа к защите от угроз Майкрософт без пользователя
keywords: приложение, доступ, API, создание
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
ms.openlocfilehash: 57ba0eb77ccb855cc0c0224b5321f11809e21ae8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201423"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a><span data-ttu-id="d4e26-104">Создание приложения для доступа к защите от угроз Майкрософт без пользователя</span><span class="sxs-lookup"><span data-stu-id="d4e26-104">Create an app to access Microsoft Threat Protection without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d4e26-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d4e26-105">**Applies to:**</span></span>
- <span data-ttu-id="d4e26-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="d4e26-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="d4e26-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="d4e26-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d4e26-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="d4e26-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d4e26-109">На этой странице описано, как создать приложение для получения программного доступа к защите от угроз Майкрософт без участия пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4e26-109">This page describes how to create an application to get programmatic access to Microsoft Threat Protection without a user.</span></span> <span data-ttu-id="d4e26-110">Если вам необходим программный доступ к защите от угроз Майкрософт от имени пользователя, обратитесь [к разделу Получение доступа с помощью контекста пользователя](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="d4e26-110">If you need programmatic access to Microsoft Threat Protection on behalf of a user, see [Get access with user context](api-create-app-user-context.md).</span></span> <span data-ttu-id="d4e26-111">Если вы не знаете, какой необходим доступ, ознакомьтесь со [статьей начало работы](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="d4e26-111">If you are not sure which access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="d4e26-112">Защита от угроз Майкрософт предоставляет множество своих данных и действий через набор программных интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="d4e26-112">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="d4e26-113">Эти API помогут вам автоматизировать рабочие процессы и внедрять их на основе возможностей защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d4e26-113">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="d4e26-114">Для доступа к API требуется проверка подлинности OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="d4e26-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="d4e26-115">Для получения дополнительных сведений см [код авторизации OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="d4e26-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="d4e26-116">В общем случае необходимо выполнить следующие действия, чтобы использовать API:</span><span class="sxs-lookup"><span data-stu-id="d4e26-116">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="d4e26-117">Создайте приложение Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d4e26-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="d4e26-118">Получение маркера доступа с помощью этого приложения.</span><span class="sxs-lookup"><span data-stu-id="d4e26-118">Get an access token using this application.</span></span>
- <span data-ttu-id="d4e26-119">Используйте маркер для доступа к API защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d4e26-119">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="d4e26-120">В этой статье объясняется, как создать приложение Azure AD, получить маркер доступа для защиты от угроз Майкрософт и проверить маркер.</span><span class="sxs-lookup"><span data-stu-id="d4e26-120">This article explains how to create an Azure AD application, get an access token to Microsoft Threat Protection, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="d4e26-121">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="d4e26-121">Create an app</span></span>

1. <span data-ttu-id="d4e26-122">Войдите в [Azure](https://portal.azure.com) с помощью пользователя с ролью **глобального администратора** .</span><span class="sxs-lookup"><span data-stu-id="d4e26-122">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="d4e26-123">Перейдите к разделу Регистрация приложений **Azure Active Directory**с  >  **App registrations**  >  **новой регистрацией**.</span><span class="sxs-lookup"><span data-stu-id="d4e26-123">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Изображение Microsoft Azure и переход к регистрации приложения](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="d4e26-125">В форме регистрации выберите имя приложения и нажмите кнопку **зарегистрировать**.</span><span class="sxs-lookup"><span data-stu-id="d4e26-125">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="d4e26-126">Чтобы разрешить приложению доступ к защите от угроз Майкрософт и назначить ей разрешения, на странице приложения выберите **разрешения API**  >  **Добавление**разрешений  >  **API "Моя организация использует** >", введите **Microsoft Threat protection**, а затем выберите **Microsoft Threat protection**.</span><span class="sxs-lookup"><span data-stu-id="d4e26-126">To enable your app to access Microsoft Threat Protection and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and then select **Microsoft Threat Protection**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d4e26-127">Защита от угроз Майкрософт не отображается в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="d4e26-127">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="d4e26-128">Чтобы отобразить его имя, необходимо сначала начать его ввод в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="d4e26-128">You need to start writing its name in the text box to see it appear.</span></span>

   ![Изображение доступа к API и выбора API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="d4e26-130">Выберите **разрешения приложений** > выберите соответствующие разрешения для вашего сценария, например, " **инцидент. Read. ALL**", а затем выберите **Добавить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="d4e26-130">Select **Application permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read.All**, and then select **Add permissions**.</span></span>

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

    >[!NOTE]
    ><span data-ttu-id="d4e26-132">Необходимо выбрать соответствующие разрешения для вашего сценария, например, **"читать все инциденты"** — только пример.</span><span class="sxs-lookup"><span data-stu-id="d4e26-132">You need to select the relevant permissions for your scenario, **'Read all incidents'** is just an example.</span></span> <span data-ttu-id="d4e26-133">Чтобы определить, какое разрешение необходимо, просмотрите раздел **разрешения** в API, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="d4e26-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="d4e26-134">Выберите **согласие Grant**.</span><span class="sxs-lookup"><span data-stu-id="d4e26-134">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d4e26-135">Каждый раз, когда вы добавляете разрешение, необходимо выбрать разрешение **Grant Grant** , чтобы новое разрешение вступило в силу.</span><span class="sxs-lookup"><span data-stu-id="d4e26-135">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![Изображение разрешений GRANT](../../media/grant-consent.PNG)

6. <span data-ttu-id="d4e26-137">Чтобы добавить секрет в приложение, выберите **сертификаты & секреты**, добавьте описание к секрету, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d4e26-137">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4e26-138">После того как вы нажмите кнопку **Добавить**, выберите **Копировать созданное секретное значение**.</span><span class="sxs-lookup"><span data-stu-id="d4e26-138">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="d4e26-139">После выхода вы не сможете получить это значение.</span><span class="sxs-lookup"><span data-stu-id="d4e26-139">You won't be able to retrieve this value after you leave.</span></span>

    ![Изображение ключа "создать приложение"](../../media/webapp-create-key2.png)

7. <span data-ttu-id="d4e26-141">Запишите идентификатор своего приложения и идентификатор клиента.</span><span class="sxs-lookup"><span data-stu-id="d4e26-141">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="d4e26-142">На странице приложения перейдите в раздел **Overview (обзор** ) и скопируйте приведенный ниже пример.</span><span class="sxs-lookup"><span data-stu-id="d4e26-142">On your application page, go to **Overview** and copy the following.</span></span>

   ![Изображение идентификатора созданного приложения](../../media/app-and-tenant-ids.png)

8. <span data-ttu-id="d4e26-144">**Только для партнеров Майкрософт по защите от угроз**.</span><span class="sxs-lookup"><span data-stu-id="d4e26-144">**For Microsoft Threat Protection Partners only**.</span></span> <span data-ttu-id="d4e26-145">[Следуйте инструкциям в этой статье](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span><span class="sxs-lookup"><span data-stu-id="d4e26-145">[Follow the instructions here](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span></span> <span data-ttu-id="d4e26-146">Настройте приложение для нескольких клиентов (доступно во всех клиентах после согласия).</span><span class="sxs-lookup"><span data-stu-id="d4e26-146">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="d4e26-147">Это **необходимо** для сторонних приложений (например, при создании приложения, предназначенного для запуска в клиенте с несколькими клиентами).</span><span class="sxs-lookup"><span data-stu-id="d4e26-147">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="d4e26-148">Это **не требуется** , если вы создаете службу, которую нужно запустить только в своем клиенте (например, если вы создаете приложение для собственного использования, которое будет работать только с собственными данными).</span><span class="sxs-lookup"><span data-stu-id="d4e26-148">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="d4e26-149">Чтобы настроить приложение для поддержки нескольких клиентов:</span><span class="sxs-lookup"><span data-stu-id="d4e26-149">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="d4e26-150">Перейдите к разделу **Проверка подлинности**и добавьте в https://portal.azure.com качестве **URI перенаправления**.</span><span class="sxs-lookup"><span data-stu-id="d4e26-150">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="d4e26-151">В нижней части страницы в разделе **Поддерживаемые типы учетных записей**выберите **учетные записи в любом** согласии приложения каталога организации для приложения с несколькими клиентами.</span><span class="sxs-lookup"><span data-stu-id="d4e26-151">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="d4e26-152">Приложение должно быть утверждено в каждом клиенте, где вы планируете его использовать.</span><span class="sxs-lookup"><span data-stu-id="d4e26-152">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="d4e26-153">Это связано с тем, что ваше приложение взаимодействует с защитой от угроз Майкрософт от имени клиента.</span><span class="sxs-lookup"><span data-stu-id="d4e26-153">This is because your application interacts Microsoft Threat Protection on behalf of your customer.</span></span>

    <span data-ttu-id="d4e26-154">Вы (или ваш клиент, если вы пишете стороннее приложение), должны выбрать ссылку согласие и одобрить ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="d4e26-154">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="d4e26-155">Разрешение следует выполнять у пользователя с правами администратора в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d4e26-155">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="d4e26-156">Ссылка на согласие выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d4e26-156">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="d4e26-157">Где 00000000-0000-0000-0000-000000000000 заменяется ИДЕНТИФИКАТОРом приложения.</span><span class="sxs-lookup"><span data-stu-id="d4e26-157">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="d4e26-158">**Договорились!**</span><span class="sxs-lookup"><span data-stu-id="d4e26-158">**Done!**</span></span> <span data-ttu-id="d4e26-159">Вы успешно зарегистрировали приложение!</span><span class="sxs-lookup"><span data-stu-id="d4e26-159">You have successfully registered an application!</span></span> <span data-ttu-id="d4e26-160">В примерах ниже показано, как для получения и проверки маркера.</span><span class="sxs-lookup"><span data-stu-id="d4e26-160">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="d4e26-161">Получение токена доступа</span><span class="sxs-lookup"><span data-stu-id="d4e26-161">Get an access token</span></span>

<span data-ttu-id="d4e26-162">Более подробную информацию о маркерах Azure AD можно узнать в [руководстве по Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="d4e26-162">For more details on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="d4e26-163">Воспользуйтесь PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4e26-163">Use PowerShell</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

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

### <a name="use-c"></a><span data-ttu-id="d4e26-164">Используйте C#:</span><span class="sxs-lookup"><span data-stu-id="d4e26-164">Use C#:</span></span>

<span data-ttu-id="d4e26-165">Приведенный ниже код был протестирован с использованием NuGet Microsoft. IdentityModel. Clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="d4e26-165">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="d4e26-166">Создайте новое консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="d4e26-166">Create a new console application.</span></span>
1. <span data-ttu-id="d4e26-167">Установите NuGet [Microsoft. IdentityModel. Clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="d4e26-167">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="d4e26-168">Добавьте следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="d4e26-168">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="d4e26-169">Скопируйте и вставьте следующий код в свое приложение (не забудьте обновить три переменные: ```tenantId, appId, appSecret``` ):</span><span class="sxs-lookup"><span data-stu-id="d4e26-169">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="d4e26-170">Использование Python</span><span class="sxs-lookup"><span data-stu-id="d4e26-170">Use Python</span></span> 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a><span data-ttu-id="d4e26-171">Использование фигурного скобки</span><span class="sxs-lookup"><span data-stu-id="d4e26-171">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="d4e26-172">В приведенной ниже процедуре предполагается, что на компьютере уже установлена функция "фигурное" для Windows.</span><span class="sxs-lookup"><span data-stu-id="d4e26-172">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="d4e26-173">Откройте командную строку и присвойте CLIENT_ID ИДЕНТИФИКАТОРу приложения Azure.</span><span class="sxs-lookup"><span data-stu-id="d4e26-173">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="d4e26-174">Задайте для CLIENT_SECRET секрета приложения Azure.</span><span class="sxs-lookup"><span data-stu-id="d4e26-174">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="d4e26-175">Присвойте TENANT_ID ИДЕНТИФИКАТОРу клиента Azure, который хочет использовать ваше приложение для доступа к защите от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d4e26-175">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft Threat Protection.</span></span>
1. <span data-ttu-id="d4e26-176">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d4e26-176">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="d4e26-177">Вы получите ответ в следующей форме:</span><span class="sxs-lookup"><span data-stu-id="d4e26-177">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="d4e26-178">Проверка маркера</span><span class="sxs-lookup"><span data-stu-id="d4e26-178">Validate the token</span></span>

<span data-ttu-id="d4e26-179">Убедитесь, что вы получили правильный маркер:</span><span class="sxs-lookup"><span data-stu-id="d4e26-179">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="d4e26-180">Скопируйте и вставьте маркер, полученный на предыдущем шаге, в [JWT](https://jwt.ms) , чтобы его можно было декодировать.</span><span class="sxs-lookup"><span data-stu-id="d4e26-180">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="d4e26-181">Проверка наличия утверждения "роли" с нужными разрешениями</span><span class="sxs-lookup"><span data-stu-id="d4e26-181">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="d4e26-182">На следующем рисунке показан Раскодированный маркер, полученный из приложения с ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` разрешениями:</span><span class="sxs-lookup"><span data-stu-id="d4e26-182">In the following image, you can see a decoded token acquired from an app with ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Изображение проверки маркера](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="d4e26-184">Использование маркера для доступа к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d4e26-184">Use the token to access Microsoft Threat Protection API</span></span>

1. <span data-ttu-id="d4e26-185">Выберите API, который хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="d4e26-185">Choose the API you want to use.</span></span> <span data-ttu-id="d4e26-186">Дополнительные сведения [см.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="d4e26-186">For more information, see [Supported Microsoft Threat Protection APIs](api-supported.md).</span></span>

2. <span data-ttu-id="d4e26-187">Задайте заголовок Authorization в HTTP-запросе, отправляемом пользователю "Bearer {token}" (Bearer является схемой авторизации).</span><span class="sxs-lookup"><span data-stu-id="d4e26-187">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>

3. <span data-ttu-id="d4e26-188">Срок действия маркера равен одному часу.</span><span class="sxs-lookup"><span data-stu-id="d4e26-188">The expiration time of the token is one hour.</span></span> <span data-ttu-id="d4e26-189">Можно отправить больше одного запроса с одним и тем же маркером.</span><span class="sxs-lookup"><span data-stu-id="d4e26-189">You can send more then one request with the same token.</span></span>

<span data-ttu-id="d4e26-190">Ниже приведен пример отправки запроса на получение списка инцидентов, **использующих C#**:</span><span class="sxs-lookup"><span data-stu-id="d4e26-190">The following is an example of sending a request to get a list of incidents **using C#**:</span></span> 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a><span data-ttu-id="d4e26-191">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="d4e26-191">Related topics</span></span>
- [<span data-ttu-id="d4e26-192">Доступ к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d4e26-192">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="d4e26-193">Доступ к защите от угроз Майкрософт с помощью контекста приложения</span><span class="sxs-lookup"><span data-stu-id="d4e26-193">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="d4e26-194">Доступ к защите от угроз Майкрософт с помощью контекста пользователя</span><span class="sxs-lookup"><span data-stu-id="d4e26-194">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
