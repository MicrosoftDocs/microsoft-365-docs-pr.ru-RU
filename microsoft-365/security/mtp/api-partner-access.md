---
title: Доступ к партнерам через API защиты от угроз Майкрософт
description: Узнайте, как создать приложение AAD для получения программного доступа к защите от угроз Майкрософт от имени ваших клиентов.
keywords: Partner, Access, API, многопользовательский клиент, согласие, маркер доступа, приложение
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
ms.openlocfilehash: ae9e5ae158c95ae52112f7bc16559559230a20e8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203711"
---
# <a name="partner-access-through-microsoft-threat-protection-apis"></a>Доступ к партнерам через API защиты от угроз Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

>[!IMPORTANT] 
>Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.


На этой странице описано, как создать приложение AAD для получения программного доступа к защите от угроз Майкрософт от имени ваших клиентов.

Защита от угроз Майкрософт предоставляет множество своих данных и действий через набор программных интерфейсов API. Эти API помогут вам автоматизировать рабочие процессы и внедрять их на основе возможностей защиты от угроз Майкрософт. Для доступа к API требуется проверка подлинности OAuth 2.0. Для получения дополнительных сведений см [код авторизации OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

В общем случае необходимо выполнить следующие действия, чтобы использовать API:
- Создайте приложение AAD с **несколькими клиентами** .
- Получите авторизованного (согласия) у администратора клиентов, чтобы ваше приложение получило доступ к ресурсам защиты от угроз Майкрософт.
- Получение маркера доступа с помощью этого приложения.
- Используйте маркер для доступа к API защиты от угроз Майкрософт.

Ниже приведены инструкции по созданию приложения AAD, получению маркера доступа к защите от угроз Майкрософт и проверке маркера.

## <a name="create-the-multi-tenant-app"></a>Создание приложения с несколькими клиентами

1. Войдите в [клиент Azure](https://portal.azure.com) с помощью учетной записи пользователя с ролью **глобального администратора** .

2. Перейдите к разделу Регистрация приложений **Azure Active Directory**с  >  **App registrations**  >  **новой регистрацией**. 

   ![Изображение Microsoft Azure и переход к регистрации приложения](../../media/atp-azure-new-app2.png)

3. В форме регистрации:

    - Выберите имя для своего приложения.

    - Поддерживаемые типы учетных записей — учетные записи в любом организационном каталоге.

    - URI перенаправления — тип: Web, URI: https://portal.azure.com

    ![Изображение регистрации приложения-партнера Microsoft Azure](../../media/atp-api-new-app-partner.png)


4. Разрешите приложению получить доступ к защите от угроз Майкрософт и назначьте ему минимальный набор разрешений, необходимых для выполнения интеграции.

   - На странице приложения щелкните **разрешения API**  >  **Добавление разрешений**  >  **интерфейсы API для моей организации используется** > введите **Microsoft Threat protection** и щелкните элемент **Защита от угроз Майкрософт**.

   >[!NOTE]
   >Защита от угроз Майкрософт не отображается в исходном списке. Чтобы отобразить его имя, необходимо сначала начать его ввод в текстовое поле.

   ![Изображение доступа к API и выбора API](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a>Разрешения API Request

   Чтобы определить, какое разрешение необходимо, просмотрите раздел **разрешения** в API, который вы хотите вызвать. 

   В следующем примере мы будем использовать разрешение **"чтение всех происшествий"** :

   Выберите **разрешения для приложений**  >  **происшествий. Read. ALL** > нажмите кнопку **Добавить разрешения**

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)


5. Щелкните **разрешение GRANT**

    >[!NOTE]
    >Каждый раз при добавлении разрешения необходимо щелкнуть разрешение **Grant** , чтобы новое разрешение вступило в силу.

    ![Изображение разрешений GRANT](../../media/grant-consent.PNG)

6. Добавьте секрет в приложение.

    - Щелкните **сертификаты & секреты**, добавьте описание для секрета и нажмите кнопку **Добавить**.

    >[!IMPORTANT]
    > После нажатия кнопки **Добавить** **скопируйте созданное значение секрета**. Вы не сможете получить его после выхода из!

    ![Изображение ключа "создать приложение"](../../media/webapp-create-key2.png)

7. Запишите идентификатор приложения:

   - На странице приложения перейдите в раздел **Overview (обзор** ) и скопируйте следующее:

   ![Изображение идентификатора созданного приложения](../../media/app-id.png)

8. Добавьте приложение в клиент клиента.

    Приложение должно быть утверждено в каждом клиенте, где вы планируете его использовать. Это связано с тем, что ваше приложение взаимодействует с приложением защиты от угроз Майкрософт от имени вашего клиента.

    Пользователь с **глобальным администратором** от клиента клиента должен щелкнуть ссылку "согласие" и одобрить ваше приложение.

    Ссылка на согласие имеет следующий вид:

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Где 00000000-0000-0000-0000-000000000000 следует заменять ИДЕНТИФИКАТОРом приложения

    После нажатия ссылки "согласие" Войдите в систему с глобальным администратором клиента клиента и додаст ему согласие приложения.

    ![Изображение согласия](../../media/app-consent-partner.png)

    Кроме того, вам потребуется запросить у клиента идентификатор клиента и сохранить его для последующего использования при получении маркера.

- **Договорились!** Вы успешно зарегистрировали приложение! 
- В примерах ниже показано, как для получения и проверки маркера.

## <a name="get-an-access-token-examples"></a>Получение примеров маркеров доступа:

>[!NOTE]
> Чтобы получить маркер доступа от имени клиента, используйте идентификатор клиента клиента при получении следующего маркера.

<br>Дополнительные сведения о маркере AAD можно найти в [руководстве по AAD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-powershell"></a>Использование PowerShell

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

### <a name="using-c"></a>С помощью C#:

>Приведенный ниже код был протестирован с NuGet Microsoft. IdentityModel. Clients. ActiveDirectory.

- Создание консольного приложения
- Установка NuGet [Microsoft. IdentityModel. Clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- Добавьте приведенные ниже функции с помощью

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- Скопируйте или вставьте приведенный ниже код в приложение (не забудьте обновить 3 переменные: ```tenantId, appId, appSecret``` )

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string mtpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(mtpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```



### <a name="using-curl"></a>Использование функции "перелистывание"

> [!NOTE]
> Приведенная ниже процедура предполагает, что на компьютере уже установлена функция "фигурное" для Windows "

- Открытие командного окна
- Задание CLIENT_ID ИДЕНТИФИКАТОРу приложения Azure
- Установка CLIENT_SECRET для секрета приложения Azure
- Присвойте TENANT_ID ИДЕНТИФИКАТОРу клиента Azure, который хочет использовать ваше приложение для доступа к приложению защиты от угроз Майкрософт
- Выполните приведенную ниже команду.

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Вы получите ответ на форму:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Проверка маркера

Санити убедитесь, что вы получили правильный маркер:

- Копирование и вставка в [JWT](https://jwt.ms) маркер, полученный на предыдущем шаге, чтобы декодировать его
- Проверка того, что вы получили утверждение "roles" с нужными разрешениями
- На снимке экрана ниже показан Раскодированный маркер, полученный из приложения с несколькими разрешениями для защиты от угроз Майкрософт.
- "TID" — это идентификатор клиента, которому принадлежит маркер.

![Изображение проверки маркера](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a>Использование маркера для доступа к API защиты от угроз Майкрософт

- Выберите API, который хотите использовать, для получения дополнительных сведений см. [Поддерживаемые API Microsoft Threat protection](api-supported.md)
- Задайте заголовок Authorization в HTTP-запросе, отправляемом пользователю "Bearer {token}" (Bearer — схема авторизации).
- Срок действия маркера составляет 1 час (можно отправить больше одного запроса с тем же маркером)

- Пример отправки запроса на получение списка инцидентов **с помощью C#** 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="related-topics"></a>Связанные статьи 

- [Доступ к API защиты от угроз Майкрософт](api-access.md)
- [Доступ к защите от угроз Майкрософт с помощью контекста приложения](api-create-app-web.md)
- [Доступ к защите от угроз Майкрософт с помощью контекста пользователя](api-create-app-user-context.md)
