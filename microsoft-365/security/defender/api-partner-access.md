---
title: Доступ партнеров Microsoft 365 API Defender
description: Узнайте, как создать приложение, чтобы получить программный доступ к Microsoft 365 Defender от имени пользователей.
keywords: партнер, доступ, api, мульти-клиент, согласие, маркер доступа, приложение
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
ms.openlocfilehash: 46876fef8a0279ee350d57fdc85aeced82696656
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070077"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Создание приложения с партнерским доступом Microsoft 365 API Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

На этой странице описывается создание приложения Azure Active Directory, которое имеет программный доступ к Microsoft 365 Defender от имени пользователей нескольких клиентов. Приложения с несколькими клиентами полезны для обслуживания больших групп пользователей.

Если вам необходим программный доступ к Microsoft 365 Defender от имени одного пользователя, см. в раздел Создание приложения для доступа Microsoft 365 API Defender от [имени пользователя.](api-create-app-user-context.md) Если вам необходим доступ без явно определенного пользователя (например, если вы пишете фоновое приложение или daemon), см. статью Создание приложения для доступа к Microsoft 365 Defender без [пользователя](api-create-app-web.md). Если вы не уверены, какой доступ вам нужен, см. [в этой ленте Начало](api-access.md)работы.

Microsoft 365 Defender предоставляет большую часть своих данных и действий с помощью набора программных API. Эти API помогают автоматизировать рабочий процесс и использовать возможности Microsoft 365 Defender. Этот доступ к API требует проверки подлинности OAuth2.0. Дополнительные сведения см. [в тексте OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

В общем, для использования этих API необходимо предпринять следующие действия:

- Создание приложения Azure Active Directory Azure AD.
- Получение маркера доступа с помощью этого приложения.
- Используйте маркер для доступа к API Microsoft 365 Defender.

Так как это приложение является нескольким клиентом, вам также потребуется согласие администратора от каждого клиента от имени его пользователей. [](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant)

В этой статье объясняется, как:

- Создание **многоканального приложения** Azure AD
- Получите авторизованный согласие администратора пользователя на доступ к необходимому Microsoft 365 Defender.
- Получите маркер доступа к Microsoft 365 Defender
- Проверка маркера

Microsoft 365 Defender предоставляет большую часть своих данных и действий с помощью набора программных API. Эти API помогут автоматизировать потоки работы и вносимые Microsoft 365 Defender. Доступ к API требует проверки подлинности OAuth2.0. Дополнительные сведения см. [в тексте OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

В общем, для использования API необходимо предпринять следующие действия:

- Создание приложения Azure AD с **несколькими** клиентами.
- Получите авторизованный (согласие) администратор пользователя для приложения для доступа Microsoft 365 Defender.
- Получение маркера доступа с помощью этого приложения.
- Используйте маркер для доступа к API Microsoft 365 Defender.

В следующих действиях вы можете узнать, как создать многоканальный приложение Azure AD, получить маркер доступа Microsoft 365 Defender и проверить маркер.

## <a name="create-the-multi-tenant-app"></a>Создание приложения с несколькими клиентами

1. Во входе [в Azure](https://portal.azure.com) в качестве пользователя с **ролью глобального администратора.**

2. Перейдите **к Azure Active Directory**  >  **регистрации Приложений** Новая  >  **регистрация**.

   ![Изображение Microsoft Azure и навигации для регистрации приложений](../../media/atp-azure-new-app2.png)

3. В форме регистрации:

   - Выберите имя приложения.
   - Из **поддерживаемых типов учетных** записей выберите учетные записи в любом организационном каталоге **(любой каталог Azure AD) — Multitenant**.
   - Заполните раздел **URI перенаправления.** Выберите **веб-тип** и дайте URI перенаправления как **https://portal.azure.com** .

   После заполнения формы выберите Register **.**

   ![Изображение формы приложения Register](../..//media/atp-api-new-app-partner.png)

4. На странице приложения выберите **API Permissions** Add permission API, которые моя организация использует  >    >   >, **введите** Защита от угроз (Майкрософт) и выберите **Защита от угроз (Майкрософт)**. Теперь приложение может получить доступ к Microsoft 365 Defender.

   > [!TIP]
   > *Защита от угроз (Майкрософт)* является прежним именем Microsoft 365 Defender и не будет отображаться в исходном списке. Чтобы увидеть его, необходимо приступить к написанию его имени в текстовом окне.

   ![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)

5. Выберите **разрешения приложения.** Выберите соответствующие разрешения для сценария (например, **Incident.Read.All),** а затем добавьте **разрешения.**

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Необходимо выбрать соответствующие разрешения для сценария. *Чтение всех инцидентов* — это только пример. Чтобы определить, какое разрешение вам нужно, обратите внимание на раздел **Разрешения** в API, который вы хотите вызвать.
    >
    > Например, для [запуска расширенных запросов](api-advanced-hunting.md)выберите разрешение "Запуск расширенных запросов"; чтобы [изолировать устройство,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)выберите разрешение "Изолировать машину".

6. Выберите **согласие администратора Гранта**. Каждый раз, когда вы добавляете разрешение, необходимо выбрать согласие администратора **Гранта,** чтобы оно вступает в силу.

    ![Изображение разрешений гранта](../../media/grant-consent.PNG)

7. Чтобы добавить секрет в приложение, выберите сертификаты **&,** добавьте описание в секрет, а затем выберите **Добавить**.

    > [!TIP]
    > После выбора **Добавить** выберите **скопируйте сгенерированную секретную ценность.** Вы не сможете получить секретное значение после того, как вы уйдете.

    ![Изображение ключа создания приложения](../../media/webapp-create-key2.png)

8. Запись ID приложения и ID клиента в безопасном месте. Они перечислены в статье **Обзор на** странице приложения.

   ![Изображение созданного id приложения](../../media/app-and-tenant-ids.png)

9. Добавьте приложение в клиент пользователя.

   Так как приложение взаимодействует с Microsoft 365 Defender от имени пользователей, оно должно быть утверждено для каждого клиента, на котором вы собираетесь его использовать.

   Глобальный **администратор** из клиента пользователя должен просмотреть ссылку согласия и утвердить ваше приложение.

   Ссылка согласие имеет форму:

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   Цифры `00000000-0000-0000-0000-000000000000` должны быть заменены на код приложения.

   Нажав на ссылку согласие, войдите в глобальный администратор клиента пользователя и согласите приложение.

   ![Изображение согласия](../../media/app-consent-partner.png)

   Кроме того, необходимо задать пользователю свой ID клиента. Идентификатор клиента является одним из идентификаторов, используемых для приобретения маркеров доступа.

- **Договорились!** Вы успешно зарегистрировали приложение!
- Ниже приведены примеры приобретения и проверки маркеров.

## <a name="get-an-access-token"></a>Получение токена доступа

Дополнительные сведения о маркерах Azure AD см. в руководстве [Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> Хотя в примерах этого раздела рекомендуется вклеить секретные значения  для целей тестирования, никогда не следует секретов жесткого кода в приложение, запущенное в производстве. Третья сторона может использовать ваш секрет для доступа к ресурсам. Вы можете помочь сохранить секреты вашего приложения в безопасности с помощью [Хранилища ключей Azure.](/azure/key-vault/general/about-keys-secrets-certificates) Пример того, как защитить приложение, см. в примере Управление секретами в серверных приложениях [с помощью хранилища ключей Azure.](/learn/modules/manage-secrets-with-azure-key-vault/)

> [!TIP]
> В следующих примерах используйте пользовательский ID клиента, чтобы проверить, работает ли сценарий.

### <a name="get-an-access-token-using-powershell"></a>Получить маркер доступа с помощью PowerShell

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

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
1. Установка NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Добавьте следующую строку:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Скопируйте и вклейте в приложение следующий код (не забудьте обновить три переменные: `tenantId` `clientId` , , `appSecret` ):

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

### <a name="get-an-access-token-using-curl"></a>Получить маркер доступа с помощью завитка

> [!NOTE]
> Curl предварительно установлен на Windows 10 версии 1803 и более поздней версии. Для других версий Windows скачайте и установите средство непосредственно с [официального веб-сайта curl.](https://curl.haxx.se/windows/)

1. Откройте командную подсказку и установите CLIENT_ID к вашему ID приложения Azure.
1. Установите CLIENT_SECRET для секрета приложения Azure.
1. Установите TENANT_ID имя клиента Azure для пользователя, который хочет использовать приложение для доступа к Microsoft 365 Defender.
1. Выполните следующую команду:

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Успешный ответ будет выглядеть так:

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Проверка маркера

1. Скопируйте и вклеите маркер на веб-сайт валидатора веб-маркеров [JSON JWT,](https://jwt.ms) чтобы расшифровать его.
1. Убедитесь, что *утверждение ролей* в расшифроваемом маркере содержит нужные разрешения.

На следующем изображении можно увидеть расшифровав маркер, приобретенный из приложения, с разрешениями и ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` разрешениями:

![Изображение проверки маркеров](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Используйте маркер для доступа к API Microsoft 365 Defender

1. Выберите API, который вы хотите использовать (инциденты или расширенный поиск). Дополнительные сведения см. в [Microsoft 365 API Defender.](api-supported.md)
2. В http-запросе, который вы отправляете, задайте загон авторизации , Bearer является схемой авторизации, а маркер - `"Bearer" <token>` проверенным маркером.  
3. Срок действия маркера истекает в течение одного часа. За это время вы можете отправить несколько запросов с одним маркером.

В следующем примере показано, как отправить запрос для получения списка инцидентов **с C#**.

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Связанные статьи

- [Microsoft 365 Обзор API defender](api-overview.md)
- [Доступ к API Microsoft 365 Defender](api-access.md)
- [Создание приложения "Hello world"](api-hello-world.md)
- [Создание приложения для доступа Microsoft 365 Defender без пользователя](api-create-app-web.md)
- [Создание приложения для доступа Microsoft 365 API Defender от имени пользователя](api-create-app-user-context.md)
- [Узнайте о ограничениях API и лицензировании](api-terms.md)
- [Понимание кодов ошибок](api-error-codes.md)
- [Управление секретами в приложениях сервера с помощью хранилища ключей Azure](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Авторизация OAuth 2.0 для входов пользователей и доступа к API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)