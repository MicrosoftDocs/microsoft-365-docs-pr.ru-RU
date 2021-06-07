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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6182b4cb0d1f648f33c3a7fc4da4c648d8996bcd
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770617"
---
# <a name="partner-access-through-microsoft-defender-for-endpoint-apis"></a>Доступ партнера через API Endpoint Defender для Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

На этой странице описывается создание приложения Azure Active Directory Azure AD для получения программного доступа к Microsoft Defender для конечной точки от имени клиентов.


Microsoft Defender для конечной точки предоставляет большую часть своих данных и действий с помощью набора программных API. Эти API помогут автоматизировать потоки работы и вносимые новые решения на основе возможностей Microsoft Defender для конечных точек. Доступ к API требует проверки подлинности OAuth2.0. Дополнительные сведения см. [в тексте OAuth 2.0 Authorization Code Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

В общем, для использования API необходимо предпринять следующие действия:
- Создание приложения Azure AD с **несколькими** клиентами.
- Получите авторизованный (согласие) администратор клиента для приложения для доступа к ресурсам Defender для конечных точек, которые ему необходимы.
- Получение маркера доступа с помощью этого приложения.
- С помощью маркера можно получить доступ к API Microsoft Defender для конечной точки.

В следующих действиях вы сможете узнать, как создать приложение Azure AD, получить маркер доступа в Microsoft Defender для конечной точки и проверить маркер.

## <a name="create-the-multi-tenant-app"></a>Создание приложения с несколькими клиентами

1. Во входе в [клиент Azure с](https://portal.azure.com) пользователем, который имеет роль **глобального администратора.**

2. Перейдите **к Azure Active Directory**  >  **регистрации Приложений** Новая  >  **регистрация**. 

   ![Изображение Microsoft Azure и навигации для регистрации приложений](images/atp-azure-new-app2.png)

3. В форме регистрации:

    - Выберите имя приложения.

    - Поддерживаемые типы учетных записей — учетные записи в любом организационном каталоге.

    - Перенаправление URI — тип: Web, URI: https://portal.azure.com

    ![Изображение регистрации Microsoft Azure партнеров](images/atp-api-new-app-partner.png)


4. Разрешить приложению доступ к Microsoft Defender для конечной точки и назначить его с минимальным набором разрешений, необходимых для завершения интеграции.

   - На странице приложения выберите **API Permissions** Add  >  **permissionS** my  >  **organization uses** > **WindowsDefenderATP** и выберите в **WindowsDefenderATP**.

   - **Примечание.** *WindowsDefenderATP* не появляется в исходном списке. Начните писать свое имя в текстовом окне, чтобы увидеть его.

   ![добавление разрешений](images/add-permission.png)
   
   ### <a name="request-api-permissions"></a>Запрос разрешений API

   Чтобы определить, какое разрешение вам нужно, просмотрите раздел **Разрешения** в API, который вы хотите вызвать. Например:

   - Чтобы [запускать расширенные запросы,](run-advanced-query-api.md)выберите разрешение "Запуск расширенных запросов"
   
   - Чтобы [изолировать устройство,](isolate-machine.md)выберите разрешение "Изолировать машину"

   В следующем примере мы будем использовать **разрешение "Чтение всех оповещений":**

   Выбор **разрешений**  >  **приложения Alert.Read.All >** в **приложении Add permissions**

   ![разрешения для приложений](images/application-permissions.png)


5. Выберите **согласие гранта**

    - **Примечание.** Каждый раз, когда вы добавляете разрешение, необходимо выбрать по согласию **гранта,** чтобы новое разрешение вступает в силу.

    ![Изображение разрешений гранта](images/grant-consent.png)

6. Добавьте секрет в приложение.

    - Выберите **сертификаты &,** добавьте описание в секрет и выберите **Добавить**.

    **Важно.** После щелчка Добавить **скопируйте сгенерированную секретную ценность.** Вы не сможете получить после того, как уйдете!

    ![Изображение ключа создания приложения](images/webapp-create-key2.png)

7. Запишите свой ID приложения:

   - На странице приложения перейдите в **Обзор и** скопируйте следующую информацию:

   ![Изображение созданного id приложения](images/app-id.png)

8. Добавьте приложение клиенту.

    Необходимо, чтобы ваше приложение было утверждено в каждом клиенте, где вы собираетесь его использовать. Это происходит потому, что ваше приложение взаимодействует с приложением Microsoft Defender для конечной точки от имени клиента.

    Пользователь с **глобальным администратором** из клиента клиента должен выбрать ссылку на согласие и утвердить ваше приложение.

    Ссылка согласие имеет форму:

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Где 00000000-0000-0000-0000-00000000000 следует заменить вашим ИД приложения

    Нажав на ссылку согласие, войдите в глобальный администратор клиента клиента и согласиться с приложением.

    ![Изображение согласия](images/app-consent-partner.png)

    Кроме того, при приобретении маркера необходимо спросить у клиента его ИД клиента и сохранить его для дальнейшего использования.

- **Договорились!** Вы успешно зарегистрировали приложение! 
- Ниже приведены примеры приобретения и проверки маркеров.

## <a name="get-an-access-token-example"></a>Пример маркера доступа:

**Примечание:** Чтобы получить маркер доступа от имени клиента, используйте ID клиента в следующих приобретениях маркеров.

<br>Дополнительные сведения о маркере AAD см. в [учебнике AAD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-powershell"></a>С помощью PowerShell

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

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
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="using-c"></a>Использование C#:

>Ниже код был протестирован с помощью Nuget Microsoft.IdentityModel.Clients.ActiveDirectory

- Создание нового приложения консоли
- Установка NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- Добавление приведенного ниже использования

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- Copy/Paste the below code in your application (do not forget to update the three variables: ```tenantId, appId, appSecret``` )

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


### <a name="using-python"></a>Использование Python

Обратитесь к [маркеру Get using Python](run-advanced-query-sample-python.md#get-token)

### <a name="using-curl"></a>Использование curl

> [!NOTE]
> Приведенная ниже процедура, предполагаемая для Windows, уже установлена на компьютере

- Откройте окно команды
- Настройка CLIENT_ID для вашего ID приложения Azure
- Настройка CLIENT_SECRET для секрета приложения Azure
- Установите TENANT_ID клиента Azure, который хочет использовать приложение для доступа к приложению Microsoft Defender для конечных точек.
- Запустите приведенную ниже команду:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Вы получите ответ формы:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Проверка маркера

Проверка вменяемости, чтобы убедиться, что вы получили правильный маркер:
- Скопируйте или вклеите [в JWT](https://jwt.ms) маркер, который вы получаете на предыдущем шаге, чтобы расшифровать его
- Проверка получения утверждения "роли" с нужными разрешениями
- На приведенной ниже скриншоте можно увидеть расшифровав маркер, приобретенный из приложения с несколькими разрешениями в Microsoft Defender для конечной точки:
- Утверждение "tid" — это ИД клиента, к которой принадлежит маркер.

![Изображение проверки маркеров](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>С помощью маркера можно получить доступ к API Endpoint Defender для Microsoft Defender

- Выберите API, который вы хотите использовать, дополнительные сведения см. в [веб-сайте Supported Microsoft Defender for Endpoint API](exposed-apis-list.md)
- Установите заглавную запись авторизации в http-запросе, который вы отправляете в "Bearer {token}" (Bearer — это схема авторизации)
- Срок действия маркера составляет 1 час (вы можете отправить несколько запросов с одним и тем же маркером)

- Пример отправки запроса для получения списка оповещений **с помощью C#** 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>См. также
- [Поддерживаемые API Microsoft Defender для конечной точки](exposed-apis-list.md)
- [Доступ к Microsoft Defender для конечной точки от имени пользователя](exposed-apis-create-app-nativeapp.md)
