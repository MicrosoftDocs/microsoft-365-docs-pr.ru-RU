---
title: Создание приложения для доступа к Microsoft 365 Defender без пользователя
description: Узнайте, как создать приложение для доступа к Microsoft 365 Defender без пользователя.
keywords: приложение, доступ, api, создание
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
ms.openlocfilehash: f438189b4ba9fb66124650782b3de2ee34dfee64
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928442"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>Создание приложения для доступа к Microsoft 365 Defender без пользователя

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

На этой странице описывается создание приложения для получения программного доступа к Microsoft 365 Defender без определенного пользователя, например, если вы создаете программу или фоновую службу.

Если вам нужен программный доступ к Microsoft 365 Defender от имени одного или более пользователей, см. статью "Создание приложения для доступа к API Microsoft [365 Defender](api-create-app-user-context.md) от имени пользователя" и создание приложения с партнерским доступом к API [Microsoft 365 Defender.](api-partner-access.md) Если вы не знаете, какой тип доступа вам нужен, см. ["Начало работы".](api-access.md)

Защитник Microsoft 365 предоставляет большую часть своих данных и действий с помощью набора программных API. Эти API помогают автоматизировать процессы и использовать возможности Защитника Microsoft 365. Для доступа к этому API требуется проверка подлинности OAuth2.0. Дополнительные сведения см. в потоке кода авторизации [OAuth 2.0.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

Как правило, для использования этих API необходимо сделать следующее:

- Создайте приложение Azure Active Directory (Azure AD).
- Получение маркера доступа с помощью этого приложения.
- Используйте маркер для доступа к API Защитника Microsoft 365.

В этой статье объясняется, как:

- Создание приложения Azure AD
- Получите маркер доступа к Защитнику Microsoft 365
- Проверка маркера.

## <a name="create-an-app"></a>Создать приложение

1. Во sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.

2. Перейдите к регистрации нового приложения **Azure Active Directory.**  >    >  

   ![Изображение Microsoft Azure и переход к регистрации приложений](../../media/atp-azure-new-app2.png)

3. В форме выберите имя приложения, а затем выберите **"Регистрация".**

4. На странице приложения выберите "API Разрешения для добавления разрешений" **API,** которые моя организация использует >, введите "Защита от угроз (Майкрософт)" и выберите "Защита от  >    >   **угроз (Майкрософт)".**  Теперь ваше приложение может получить доступ к Microsoft 365 Defender.

   > [!TIP]
   > *Защита от угроз (Майкрософт)* — это прежнее имя Защитника Microsoft 365, которое не будет отображаться в исходном списке. Чтобы увидеть, как оно появляется, необходимо начать писать его имя в текстовом поле.

   ![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)

5. Выберите **разрешения для приложений.** Выберите соответствующие разрешения для сценария (например, **Incident.Read.All),** а затем выберите **"Добавить разрешения".**

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Необходимо выбрать соответствующие разрешения для сценария. *Прочитать все инциденты* можно только в качестве примера. Чтобы определить необходимые разрешения, обратитесь к разделу **"Разрешения"** в API, который требуется вызвать.
    >
    > Например, чтобы выполнить [расширенные запросы,](api-advanced-hunting.md)выберите разрешение "Выполнение расширенных запросов"; чтобы [изолировать устройство,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)выберите разрешение "Изолировать компьютер".

6. Выберите **"Предоставить согласие администратора".** При каждом добавлении разрешения  необходимо выбрать разрешение администратора, чтобы оно вступает в силу.

    ![Изображение разрешения на предоставление](../../media/grant-consent.PNG)

7. Чтобы добавить секрет в приложение, выберите сертификаты & **секреты,** добавьте описание в секрет, а затем выберите **"Добавить".**

    > [!TIP]
    > После выбора **"Добавить"** выберите **"Скопировать сгенерированную секретную копию".** После этого вы не сможете получить значение секрета.

    ![Изображение создания ключа приложения](../../media/webapp-create-key2.png)

8. Зафиксировать свой ИД приложения и ид клиента в надежном месте. Они перечислены в списке **"Обзор"** на странице приложения.

   ![Изображение созданного ид приложения](../../media/app-and-tenant-ids.png)

9. Только для партнеров Защитника [](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) **Microsoft 365:** следуйте этим инструкциям для доступа партнеров через API Microsoft 365 Defender, задайте для вашего приложения мультиантивное, чтобы оно было доступно всем арендаторам после получения согласия администратора. Для приложений **сторонних** разработчиков необходим доступ партнеров, например, если вы создаете приложение, предназначенное для работы в клиентах нескольких клиентов. Это не **обязательно,** если вы создаете службу, которую вы хотите запускать только в клиенте, например приложение для собственного использования, которое будет взаимодействовать только с вашими данными. Чтобы сделать приложение мультиантивным, с помощью:

    - Перейдите **к проверке подлинности** и добавьте https://portal.azure.com в качестве **URI перенаправления.**

    - В нижней части страницы в области "Поддерживаемые типы учетных записей" выберите "Учетные записи" в любом приложении каталога организации, чтобы получить согласие для мульти клиента. 

    Так как ваше приложение взаимодействует с Microsoft 365 Defender от имени пользователей, оно должно быть утверждено для каждого клиента, в котором вы собираетесь его использовать.

    Глобальный администратор Active Directory для каждого клиента должен выбрать ссылку на согласие и утвердить ваше приложение.

    Ссылка согласия имеет следующую структуру:

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    Цифры `00000000-0000-0000-0000-000000000000` должны быть заменены вашим ИД приложения.  

**Договорились!** Вы успешно зарегистрировали приложение! Примеры получения и проверки маркеров см. в примерах ниже.

## <a name="get-an-access-token"></a>Получение токена доступа

Дополнительные сведения о маркерах Azure Active Directory см. в руководстве [по Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> Несмотря на то что в примерах в этом разделе рекомендуется в  секрете в целях тестирования вовать секретные значения, никогда не следует жестко кодировать секреты в приложение, запущенное в производственной области. Третья сторона может использовать ваш секрет для доступа к ресурсам. Вы можете обеспечить безопасность секретов приложения с помощью [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates) Практический пример того, как можно защитить приложение, см. в под управлением секретов в серверных приложениях [с помощью Azure Key Vault.](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)

### <a name="get-an-access-token-using-powershell"></a>Получить маркер доступа с помощью PowerShell

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

### <a name="get-an-access-token-using-c"></a>Получить маркер доступа с помощью C\#

> [!NOTE]
> Следующий код был протестирован с помощью Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.

1. Создайте новое консольное приложение.

1. Установите NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory.](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)

1. Добавьте следующую строку:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Скопируйте в приложение следующий код (не забудьте обновить три переменные: `tenantId` `clientId` , , `appSecret` ):

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

### <a name="get-an-access-token-using-python"></a>Получить маркер доступа с помощью Python

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

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

### <a name="get-an-access-token-using-curl"></a>Получить маркер доступа с помощью маркера доступа

> [!NOTE]
> Она предварительно установлена в Windows 10 версии 1803 и более поздних версий. Для других версий Windows скачайте и установите средство непосредственно с [официального веб-сайта в Интернете.](https://curl.haxx.se/windows/)

1. Откройте командную подсказку и CLIENT_ID в качестве ИД приложения Azure.

1. За CLIENT_SECRET в секрете приложения Azure.

1. Задайте TENANT_ID в ИД клиента Azure, который хочет использовать ваше приложение для доступа к Защитнику Microsoft 365.

1. Выполните следующую команду:

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   Успешный ответ будет выглядеть так:

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>Проверка маркера

1. Скопируйте и в paste маркер на веб-сайте проверки веб-маркеров [JSON, JWT,](https://jwt.ms) чтобы декодировать его.

1. Убедитесь, что *утверждение ролей* внутри раскодирования маркера содержит нужные разрешения.

   На следующем изображении можно увидеть раскодный маркер, полученный из приложения, с `Incidents.Read.All` разрешениями `Incidents.ReadWrite.All` и `AdvancedHunting.Read.All` разрешениями:

   ![Изображение проверки маркера](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Использование маркера для доступа к API Защитника Microsoft 365

1. Выберите нужный API (инциденты или расширенный поиск). Дополнительные сведения см. в [поддерживаемых API Microsoft 365 Defender.](api-supported.md)

2. В http-запросе, который вы будете отправлять, задайте для загона авторизации `"Bearer" <token>` *(Bearer)* схему авторизации, а маркер — ваш проверенный маркер. 

3. Срок действия маркера истекает в течение одного часа. За это время можно отправить несколько запросов с одним маркером.

В следующем примере показано, как отправить запрос, чтобы получить список инцидентов с **помощью C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Статьи по теме

- [Обзор API Microsoft 365 Defender](api-overview.md)
- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Создание приложения "Hello world"](api-hello-world.md)
- [Создание приложения для доступа к API Microsoft 365 Defender от имени пользователя](api-create-app-user-context.md)
- [Создание приложения с мультиязычным доступом партнеров к API Microsoft 365 Defender](api-partner-access.md)
- [Узнайте об ограничениях API и лицензировании](api-terms.md)
- [Коды ошибок](api-error-codes.md)
- [Управление секретами в серверных приложениях с помощью Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Авторизация OAuth 2.0 для доступа к API и входу пользователя](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
